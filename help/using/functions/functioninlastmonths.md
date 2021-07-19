---
product: adobe campaign
title: inLastMonths
description: Obtenga información sobre la función en LastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora: meses delta.

## Categoría

Fecha 

## Sintaxis de función

`inLastMonths(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastMonths(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Devuelve verdadero.
