---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: Obtenga información sobre la función en LastHours
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 12%

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
