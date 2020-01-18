---
title: toDateTime
description: Obtenga información sobre la función toDateTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---

# toDateTime {#toDateTime}

Convierte los parámetros en un valor de fecha y hora, según sus tipos.

## Categoría

Conversión

## Sintaxis de función

`toDateTime(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora en formato ISO-8601 | string |
| id de zona horaria | string |
| fecha y hora sin zona horaria | dateTimeOnly |
| valor entero de una epoch en milisegundos | integer |

>[!NOTE]
>
>La identificación del huso horario debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión. Para obtener más información sobre los tipos de datos, consulte [](../expression/data-types.md).

## Firmas y tipos devueltos

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Devuelve un **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Ejemplos

`toDateTime ("2016-08-18T23:17:59.123Z")`

Devuelve 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Devuelve 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Devuelve 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
