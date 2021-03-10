---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: Obtenga información sobre la suma de funciones
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 9%

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
