---
product: adobe campaign
title: Funciones de administración de colecciones
description: Obtenga información sobre los tipos de datos en las funciones de administración de colecciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: e0bf1a6f9c160b72da28feaca1ca52665f365630
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 2%

---

# Funciones de administración de colecciones {#collection-management-functions}

El lenguaje de expresión también introduce un conjunto de funciones para consultar colecciones.

Estas funciones se explican a continuación. En los ejemplos siguientes, vamos a utilizar la carga útil de evento que contiene una colección:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**La función &quot;all(`<condition>`)&quot;**

La función **[!UICONTROL all]** habilita la definición de un filtro en una colección determinada mediante el uso de una expresión booleana.

```
<listExpression>.all(<condition>)
```

Por ejemplo, entre todos los usuarios de la aplicación, puede obtener los que utilizan IOS 13 (expresión booleana &quot;app used == IOS 13&quot;). El resultado de esta función es la lista filtrada que contiene elementos que coinciden con la expresión booleana (ejemplo: usuario de la aplicación 1, usuario de la aplicación 34, usuario de la aplicación 432).

En una actividad Condición de fuente de datos puede comprobar si el resultado de la función **[!UICONTROL all]** es nulo o no. También puede combinar esta función **[!UICONTROL all]** con otras funciones como **[!UICONTROL count]**. Para obtener más información, consulte [Actividad de la condición de fuente de datos](../building-journeys/condition-activity.md#data_source_condition).

**Ejemplo 1:**

Queremos comprobar si un usuario ha instalado una versión específica de una aplicación. Para ello, obtenemos todos los tokens de notificación push asociados a aplicaciones móviles para las que la versión es 1.0. A continuación, realizamos una condición con la función **[!UICONTROL count]** para comprobar que la lista devuelta de tokens contiene al menos un elemento.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

El resultado es verdadero.

**Ejemplo 2:**

Aquí utilizamos la función **[!UICONTROL count]** para comprobar si hay tokens de notificación push en la colección.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

El resultado será true.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Cuando la condición de filtrado en la función **all()** está vacía, el filtro devolverá todos los elementos de la lista. **Sin embargo, para contar el número de elementos de una colección, no se requiere la función all .**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

El resultado de la expresión es **3**.

**Ejemplo 3:**

Aquí comprobamos si una persona no ha recibido ninguna comunicación en las últimas 24 horas. Filtramos la colección de eventos de experiencia recuperados de la fuente de datos de Experience Platform, utilizando dos expresiones basadas en dos elementos de la colección. En concreto, la marca de tiempo del evento se compara con dateTime devuelta por la función **[!UICONTROL nowWithDelta]**.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

El resultado será true si no hay ningún evento de experiencia que coincida con las dos condiciones.

**Ejemplo 4:**

Aquí queremos comprobar si una persona ha iniciado al menos una vez una aplicación en los últimos 7 días, por ejemplo, para enviar un déclencheur a una notificación push invitándolo a iniciar un tutorial.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** solo está disponible al manipular colecciones de eventos y  **currentDataPackField**
>al manipular colecciones de fuentes de datos. Al procesar colecciones con **[!UICONTROL all]**, **[!UICONTROL first]** y **[!UICONTROL last]**,
>en cada elemento de la colección uno a uno. **[!UICONTROL currentEventField]** y  **currentDataPackField**
>corresponde al elemento que se está reproduciendo en bucle.

**Las funciones &quot;first(`<condition>`)&quot; y &quot;last(`<condition>`)&quot;**

Las funciones **[!UICONTROL first]** y **[!UICONTROL last]** también habilitan la definición de un filtro en la colección y devuelven el primer/último elemento de la lista que cumple el filtro.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Ejemplo 1:**

Esta expresión devuelve el primer token de notificación push asociado a aplicaciones móviles para las que la versión es 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

El resultado es &quot;token_1&quot;.

**Ejemplo 2:**

Esta expresión devuelve el último token de notificación push asociado a aplicaciones móviles para las que la versión es 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

El resultado es &quot;token_2&quot;.

>[!NOTE]
>
>Los eventos de experiencia se recuperan de Adobe Experience Platform como una colección en orden cronológico inverso, por lo tanto:
>* **[!UICONTROL first]** devuelve el evento más reciente
>* **[!UICONTROL last]** devolverá la más antigua.


**Ejemplo 3:**

Comprobamos si el primer evento (más reciente) de Adobe Analytics con un valor distinto de cero para el ID de DMA tiene un valor igual a 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La función &quot;at(`<index>`)&quot;**

La función **[!UICONTROL at]** permite hacer referencia a un elemento específico de una colección según un índice.
El índice 0 es el primer índice de la colección.

_`<listExpression>`.at(`<index>`)_

**Ejemplo:**

Esta expresión devuelve el segundo token de notificación push de la lista.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

El resultado es &quot;token_2&quot;.

**Otros ejemplos**

```
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
