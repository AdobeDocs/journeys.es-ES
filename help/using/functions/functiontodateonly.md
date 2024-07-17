---
product: adobe campaign
title: toDateOnly
description: Obtenga información sobre la función toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# toDateOnly{#toDateOnly}

Convierte un valor de argumento en un valor de solo fecha.

## Categoría

Conversión

## Sintaxis de función

`toDateOnly(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha en formato ISO-8601 o &quot;AAAA-MM-DD&quot; (formato de fecha XDM) | cadena |
| fecha | fecha |

## Firmas y tipos devueltos

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

## Ejemplos

`toDateOnly("2016-08-18")`

devuelve un objeto dateOnly que representa el 18-08-2016.
