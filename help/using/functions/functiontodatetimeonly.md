---
product: adobe campaign
title: toDateTimeOnly
description: Obtenga información sobre la función toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%

---

# toDateTimeOnly{#toDateTimeOnly}

Convierte un valor de argumento en un valor de solo fecha y hora.

## Categoría

Conversión

## Sintaxis de función

`toDateTimeOnly(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora en formato ISO-8601 o &quot;AAAA-MM-DD&quot; (formato de fecha XDM) | string |
| fecha y hora | dateTime |

## Firmas y tipos devueltos

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Devolver una fecha y hora sin considerar la zona horaria.

## Ejemplos

`toDateTimeOnly ("2016-08-18")`

devuelve un dateTime que representa 2016-08-18T00:00:00 000

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
