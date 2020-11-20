---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Obtenga información sobre la función setHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

---


# setHours {#setHours}

Establece las horas de una fecha, hora u hora de fecha solamente. Por ejemplo, si desea esperar hasta una hora determinada mañana, puede forzar la hora.

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
