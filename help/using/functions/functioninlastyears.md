---
product: adobe campaign
title: inLastYears
description: Obtenga información sobre la función en LastYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastYears {#inLastYears}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora: años delta.

## Categoría

Fecha 

## Sintaxis de función

`inLastYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Devuelve verdadero.
