---
product: adobe campaign
title: Uso del editor de expresiones avanzadas
description: Aprenda a crear expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 601bed30d3c414f03c60ef52c787372e778dee54
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Ejemplos de expresiones avanzadas

El editor de expresiones avanzadas se puede utilizar para crear condiciones que le permitan filtrar usuarios en sus recorridos. Estas condiciones le permiten dirigirse a los usuarios en cuanto a tiempo, fecha, ubicación, duración o acciones como la compra o el abandono de carros, de modo que se puedan redirigir en el recorrido.

>[!NOTE]
>
>Los eventos comienzan por @, las fuentes de datos con #.

## Creación de condiciones en eventos de experiencias

El editor de expresiones avanzadas es obligatorio para realizar consultas en series temporales como una lista de compras o clics anteriores en mensajes. Estas consultas no se pueden realizar con el editor simple.

Los eventos de experiencia se recuperan de Adobe Experience Platform como una colección en orden cronológico inverso, por lo tanto:

* la primera función devolverá el evento más reciente
* la última función devolverá la más antigua.

Por ejemplo, supongamos que desea dirigirse a los clientes con un abandono del carro de compras en los últimos 7 días para enviar un mensaje cuando el cliente se acerca a una tienda, con una oferta sobre los artículos que quería que están en la tienda.

**Debe crear las siguientes condiciones:**

En primer lugar, diríjase a los clientes que hayan explorado la tienda en línea pero no hayan finalizado el pedido en los últimos 7 días.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Esta expresión busca todos los eventos para este usuario especificados en los últimos 7 días:**

A continuación, selecciona todos los eventos addtocart que no se han transformado en un completePurchase.

>[!NOTE]
>
>Para insertar campos en la expresión rápidamente, haga doble clic en el campo en el panel izquierdo del editor.

La marca de tiempo especificada actúa como valor de fecha y hora; el segundo es número de días.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Esta expresión devuelve un valor booleano.

**Ahora vamos a crear una expresión que compruebe que el producto está en existencias**

* En Inventory, esta expresión busca el campo de cantidad de un producto y especifica que debe ser bueno que 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A la derecha, se especifican los valores necesarios, aquí, necesitamos recuperar la ubicación de la tienda, que se asigna desde la ubicación del evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Y especificar SKU, utilizando la función `first` para recuperar la interacción &quot;addToCart&quot; más reciente:

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

Desde allí puede añadir otra ruta en el recorrido para cuando el producto no esté almacenado y enviar notificaciones con la oferta de participación. Configure los mensajes según corresponda y utilice datos de personalización para mejorar el destinatario de mensajes.

## Ejemplos de manipulaciones de cadenas con el editor de expresiones avanzadas

**En condiciones**

Esta condición recupera únicamente los eventos de geovalla activados en &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Explicación: Se trata de una comparación estricta de cadenas (con distinción de mayúsculas y minúsculas), equivalente a una consulta en modo simple que utiliza `equal to` con `Is sensitive` activada.

La misma consulta con `Is sensitive` si no se selecciona, se generará la siguiente expresión en modo avanzado:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**En acciones**

La siguiente expresión le permite definir el ID de CRM en un campo de personalización de acción:

```json
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         ))
```

Explicación: Este ejemplo utiliza `substr` y `lastIndexOf` funciones para eliminar llaves que encierran el ID de CRM pasado con un evento de inicio de aplicación móvil.

Para obtener más información sobre cómo utilizar el editor de expresiones avanzadas, consulte [este vídeo](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
