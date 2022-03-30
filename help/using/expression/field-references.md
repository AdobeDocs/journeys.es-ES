---
product: adobe campaign
title: Referencias de campo
description: Obtenga información sobre referencias de campo en expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 3%

---

# Referencias de campo {#concept_fkj_ll5_dgb}

Se puede adjuntar una referencia de campo a un evento o a un grupo de campos. La única información significativa es el nombre del campo y su ruta.

Si utiliza caracteres especiales en un campo, debe utilizar comillas dobles o simples. Estos son los casos en los que se necesitan comillas:

* el campo comienza con caracteres numéricos
* el campo comienza con el carácter &quot;-&quot;
* el campo contiene cualquier cosa que no sea: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Por ejemplo, si el campo es _3 h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

En la expresión, se hace referencia a los campos de evento con &quot;@&quot; y a los campos de origen de datos con &quot;#&quot;.

Se utiliza un color de sintaxis para distinguir visualmente los campos de eventos (verde) de los grupos de campos (azul).

## Valores predeterminados para referencias de campo {#default-value}

Se puede asociar un valor predeterminado con un nombre de campo. La sintaxis es la siguiente:

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>El tipo del campo y el valor predeterminado deben ser los mismos. Por ejemplo, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} no será válido porque el valor predeterminado es un número entero, mientras que el valor esperado debe ser una cadena.

Ejemplos:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

Puede añadir cualquier tipo de expresión como valor predeterminado. La única restricción es que la expresión debe devolver el tipo de datos esperado. Cuando se utiliza una función, es necesario encapsular la función con ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Referencia a un campo dentro de colecciones

Se hace referencia a los elementos definidos dentro de las colecciones mediante las funciones específicas `all`, `first` y `last`. Para obtener más información, consulte [esta página](../expression/collection-management-functions.md).

Ejemplo :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Referencia a un campo definido en un mapa

### Función  de `entry`

Para recuperar un elemento en un mapa, utilizamos la función de entrada con una clave determinada. Por ejemplo, se utiliza al definir la clave de un evento, según el espacio de nombres seleccionado. Consulte Selección del área de nombres. Para obtener más información, consulte [esta página](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

En esta expresión, se obtiene la entrada para la clave &quot;Correo electrónico&quot; del campo &quot;Mapa de identidad&quot; de un evento. La entrada &quot;Correo electrónico&quot; es una colección, de la que tomamos el &quot;id&quot; en el primer elemento utilizando &quot;first()&quot;. Para obtener más información, consulte [esta página](../expression/collection-management-functions.md).

### Función  de `firstEntryKey`

Para recuperar la primera clave de entrada de un mapa, utilice el `firstEntryKey` función.

Este ejemplo muestra cómo recuperar la primera dirección de correo electrónico de los suscriptores de una lista específica:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

En este ejemplo, la lista de suscripción tiene el nombre `daily-email`. Las direcciones de correo electrónico se definen como claves en la variable `subscribers` , que está vinculado al mapa de lista de suscripción.

### Función  de `keys`

Para recuperar todas las claves de un mapa, utilice el `keys` función.

Este ejemplo muestra cómo recuperar, para un perfil específico, todas las direcciones de correo electrónico asociadas con los suscriptores de una lista específica:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Valores de parámetro de una fuente de datos (valores dinámicos de la fuente de datos)

Si selecciona un campo de una fuente de datos externa que requiere que se llame a un parámetro, aparece una nueva pestaña a la derecha para permitirle especificar este parámetro. Consulte [esta página](../expression/expressionadvanced.md).

Para casos de uso más complejos, si desea incluir los parámetros de la fuente de datos en la expresión principal, puede definir sus valores utilizando la palabra clave _params_. Un parámetro puede ser cualquier expresión válida, incluso desde otra fuente de datos que también incluya otro parámetro.

>[!NOTE]
>
>Cuando se definen los valores de parámetro en la expresión, la pestaña de la derecha desaparece.

Utilice la siguiente sintaxis:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nombre exacto del primer parámetro de la fuente de datos.
* **`<params-1-value>`**: el valor del primer parámetro. Puede ser cualquier expresión válida.

Ejemplo:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
