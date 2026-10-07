---
product: adobe campaign
title: toDateTimeOnly
description: Obtenga información sobre la función toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
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
| fecha y hora en formato ISO-8601 o &quot;AAAA-MM-DD&quot; (formato de fecha XDM) | cadena |
| fecha y hora | dateTime |

## Firmas y tipos devueltos

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--
`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`
-->

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

## Ejemplos

`toDateTimeOnly ("2016-08-18")`

devuelve un valor dateTime que representa el valor 2016-08-18T00:00:00.000

`toDateTimeOnly(now())`

<!--
`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.
-->
