---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Obtenga información sobre la función setDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 8%

---


# setDays {#setDays}

Establece el día de una fecha, hora u hora de fecha solamente. Por ejemplo, si desea esperar hasta un día determinado del mes, puede forzar el día.

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
