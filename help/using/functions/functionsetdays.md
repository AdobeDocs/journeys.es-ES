---
product: adobe campaign
title: setDays
description: Obtenga información sobre la función setDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

---

# setDays {#setDays}

Establece el día de una fecha, hora o hora. Por ejemplo, si desea esperar hasta un día determinado del mes, puede forzar el día.

## Categoría

Fecha 

## Sintaxis de función

`setDays(<parameter>)`

## Parámetros

| Parámetro | Tipo |
|--- |--- |
| fecha y hora | dateTime |
| fecha y hora sin considerar zona horaria | dateTimeOnly |
| días | integer |

## Firmas y tipo devuelto

`setDays(<dateTime>,<days>)`

Devuelve una fecha y hora.

`setDays(<dateTimeOnly>,<days>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

## Ejemplos

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Devuelve 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
