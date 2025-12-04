---
product: adobe campaign
title: inLastMonths
description: Obtenga información sobre la función en LastMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

Devuelve true si una fecha o dateTime determinada está entre ahora y ahora (meses delta).

## Categoría

Fecha

## Sintaxis de función

`inLastMonths(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | entero |

## Firmas y tipo devuelto

`inLastMonths(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Devuelve verdadero.
