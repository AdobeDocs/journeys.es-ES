---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: Obtenga información sobre la suma de funciones
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

Devuelve un entero.

`sum(<integer>,<integer>)`

Devuelve un entero.

`sum(<decimal>,<decimal>)`

Devuelve un decimal.

## Ejemplos

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Devuelve 21.

`sum([10.5,null,8.1])`

Devuelve 18.6.
