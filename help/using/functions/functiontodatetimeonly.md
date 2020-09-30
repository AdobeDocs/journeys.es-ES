---
title: toDateTimeOnly
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
source-git-commit: 70bc6653a8cdd552a0441f4b661341d3f095b112
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# toDateTimeOnly{#toDateTimeOnly}

Convierte un valor de argumento en un valor de sólo fecha y hora.

## Categoría

Conversión

## Sintaxis de función

`toDateTimeOnly(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora en formato ISO-8601 | string |
| fecha y hora | dateTime |

## Firmas y tipos devueltos

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Devolver una fecha y hora sin tener en cuenta la zona horaria.

## Ejemplos

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Devuelve 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
