---
product: adobe campaign
title: inLastDays
description: Obtenga información sobre la función en LastDays
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 15%

---

# inLastDays {#inLastDays}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora: días delta.

## Categoría

Fecha

## Sintaxis de función

`inLastDays(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastDays(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Devuelve verdadero.
