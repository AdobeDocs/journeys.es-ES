---
product: adobe campaign
title: inLastHours
description: Obtenga información sobre la función en LastHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastHours {#inLastHours}

Devuelve verdadero si la fecha y hora dadas son entre ahora y ahora (horas delta).

## Categoría

Fecha

## Sintaxis de función

`inLastHours(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | entero |

## Firmas y tipo devuelto

`inLastHours(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Devuelve verdadero.

`inLastHours(@{MyEvent.timestamp}, 4)`

Devuelve verdadero.
