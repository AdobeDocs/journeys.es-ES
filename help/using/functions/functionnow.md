---
product: adobe campaign
title: now
description: Obtenga información acerca de la función ahora
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# now {#now}

Devuelve la fecha actual en formato de fecha y hora. Para obtener más información sobre los tipos de datos, consulte [esta página](../expression/data-types.md).

## Categoría

Fecha

## Sintaxis de función

`now(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| cadena |  |

## Firmas y tipo devuelto

`now()`

`now("<timeZone id>")`

Devuelve un valor dateTime.

## Ejemplos

`now()`

Devuelve 2019-06-03T06:30Z.

`toString(now())`

Devuelve &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Devuelve 2019-06-03T08:30+02:00.
