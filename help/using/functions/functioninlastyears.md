---
product: adobe campaign
title: inLastYears
description: Obtenga información sobre la función en LastYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastYears {#inLastYears}

Devuelve true si una fecha o dateTime determinada está entre ahora y ahora (años delta).

## Categoría

Fecha

## Sintaxis de función

`inLastYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | entero |

## Firmas y tipo devuelto

`inLastYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Devuelve verdadero.
