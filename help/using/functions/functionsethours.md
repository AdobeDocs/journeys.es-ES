---
product: adobe campaign
title: setHours
description: Obtenga información sobre la función setHours
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 9%

---

# setHours {#setHours}

Establece solo las horas de una fecha, hora u hora. Por ejemplo, si desea esperar hasta una hora determinada mañana, puede forzar la hora.

## Categoría

Fecha

## Sintaxis de función

`setHours(<parameter>)`

## Parámetros

| Parámetro | Tipo |
|--- |--- |
| fecha y hora | dateTime |
| fecha y hora sin considerar la zona horaria | dateTimeOnly |
| horas | entero |

## Firmas y tipo devuelto

`setHours(<dateTime>,<hours>)`

Devuelve una fecha y hora.

`setHours(<dateTimeOnly>,<hours>)`

Devuelve una fecha y hora sin considerar la zona horaria.

## Ejemplos

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Devuelve 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Regresa mañana a las 8:XY p.m., siendo XY los minutos en el momento de la evaluación de la hora actual. Si la evaluación se realiza a las 2:45 a. m., la hora devuelta será las 8:45 p. m.
