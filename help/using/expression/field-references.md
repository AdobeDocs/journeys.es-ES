---
title: Referencias de campo
description: Obtenga información sobre las referencias de campo en expresiones avanzadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 2af6e632461a8c01451f96c121469c9a32ae7f32
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 4%

---



# Referencias de campo {#concept_fkj_ll5_dgb}

Se puede adjuntar una referencia de campo a un evento o a un grupo de campos. La única información significativa es el nombre del campo y su ruta.

Si utiliza caracteres especiales en un campo, debe utilizar comillas simples o comillas de doble. Estos son los casos en los que se necesitan comillas:

* inicios de campo con caracteres numéricos
* los inicios de campo con el carácter &quot;-&quot;
* el campo contiene cualquier cosa que no sea: _a_-_z_, _A_-_Z_, _0_-___9, _ ,-_

Por ejemplo, si el campo es _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

En la expresión, se hace referencia a los campos de evento con &quot;@&quot; y a los campos de origen de datos con &quot;#&quot;.

Se utiliza un color de sintaxis para distinguir visualmente los campos de eventos (verde) de los grupos de campos (azul).

**Valores predeterminados para referencias de campo**

Se puede asociar un valor predeterminado al nombre de un campo. La sintaxis es la siguiente:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>El tipo del campo y el valor predeterminado deben ser los mismos. Por ejemplo, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: {2} no será válido porque el valor predeterminado es un entero, mientras que el valor esperado debe ser una cadena.

**Referencia de un campo en colecciones**

Se hace referencia a los elementos definidos dentro de las colecciones mediante las funciones específicas: todo, primero y último. Para obtener más información, consulte [esta página](../expression/collection-management-functions.md).

Ejemplo :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Referencia de un campo definido en un mapa**

Para recuperar un elemento en un mapa, utilizamos la función de entrada con una clave determinada. Por ejemplo, se utiliza al definir la clave de un evento, según la Área de nombres seleccionada. Consulte Selección de la Área de nombres. For more information, see [this page](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

En esta expresión, obtenemos la entrada para la clave de ‘Correo electrónico’ del campo ‘Mapa de identidad’ de un evento. La entrada ‘Correo electrónico’ es una colección, de la cual tomamos el ‘id’ en el primer elemento usando ‘first()’. For more information, see [this page](../expression/collection-management-functions.md).

**Valores de parámetro de una fuente de datos (valores dinámicos de la fuente de datos)**

Si selecciona un campo de un origen de datos externo que requiere que se llame a un parámetro, aparece una nueva ficha a la derecha para permitirle especificar este parámetro. Consulte [esta página](../expression/expressionadvanced.md).

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. Un parámetro puede ser cualquier expresión válida, incluso desde otra fuente de datos que también incluya otro parámetro.

>[!NOTE]
>
>Cuando define los valores de parámetro en la expresión, la ficha de la derecha desaparece.

Utilice la sintaxis siguiente:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:: nombre exacto del primer parámetro del origen de datos.
* **`<params-1-value>`**:: el valor del primer parámetro. Puede ser cualquier expresión válida.

Ejemplo:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
