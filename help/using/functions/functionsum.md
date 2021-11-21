---
product: adobe campaign
title: sum
description: Obtenga información sobre la suma de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 11%

---

# sum {#sum}

Devuelve la suma de los valores de un conjunto de expresiones. Se omiten los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`sum(<parameters>)`

## Parámetros

* listInteger
* listDecimal
* duration
* integer
* decimal

## Firmas y tipos devueltos

`sum(<listDecimal>)`

Devuelve un decimal.

`sum(<listInteger>)`

Devuelve un número entero.

`sum(<integer>,<integer>)`

Devuelve un número entero.

`sum(<decimal>,<decimal>)`

Devuelve un decimal.

## Ejemplos

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Devuelve 21.

`sum([10.5,null,8.1])`

Devuelve 18.6.
