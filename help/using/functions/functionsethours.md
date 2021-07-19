---
product: adobe campaign
title: setHours
description: Obtenga información sobre la función setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 12%

---

# setHours {#setHours}

Establece las horas de una fecha, hora u hora únicamente. Por ejemplo, si desea esperar hasta una hora determinada mañana, puede forzar la hora.

## Categoría

Fecha 

## Sintaxis de función

`setHours(<parameter>)`

## Parámetros

| Parámetro | Tipo |
|--- |--- |
| fecha y hora | dateTime |
| fecha y hora sin considerar zona horaria | dateTimeOnly |
| horas | integer |

## Firmas y tipo devuelto

`setHours(<dateTime>,<hours>)`

Devuelve una fecha y hora.

`setHours(<dateTimeOnly>,<hours>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

## Ejemplos

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Devuelve 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Regresa mañana a las 8 pm.
