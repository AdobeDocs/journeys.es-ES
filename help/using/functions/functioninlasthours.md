---
product: adobe campaign
title: inLastHours
description: Obtenga información sobre la función en LastHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 19%

---

# inLastHours {#inLastHours}

Devuelve el valor verdadero si la fecha y hora dadas está entre ahora y ahora: horas delta.

## Categoría

Fecha 

## Sintaxis de función

`inLastHours(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastHours(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Devuelve verdadero.

`inLastHours(@{MyEvent.timestamp}, 4)`

Devuelve verdadero.
