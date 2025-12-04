---
product: adobe campaign
title: sum
description: Obtenga información sobre la suma de funciones
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# sum {#sum}

Devuelve la suma de los valores de un conjunto de expresiones. Los valores nulos se omiten.

## Categoría

Agregación

## Sintaxis de función

`sum(<parameters>)`

## Parámetros

* listInteger
* listDecimal
* duration
* entero
* decimal

## Firmas y tipos devueltos

`sum(<listDecimal>)`

Devuelve un valor decimal.

`sum(<listInteger>)`

Devuelve un entero.

`sum(<integer>,<integer>)`

Devuelve un entero.

`sum(<decimal>,<decimal>)`

Devuelve un valor decimal.

## Ejemplos

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Devuelve 21.

`sum([10.5,null,8.1])`

Devuelve 18.6.
