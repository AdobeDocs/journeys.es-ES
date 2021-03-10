---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: Obtenga información sobre la función avg
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 9%

---


# avg {#avg}

Devuelve el valor promedio entre un conjunto de expresiones, dado como una lista o como dos expresiones. Se omiten los valores nulos.


## Categoría

Agregación

## Sintaxis de función

`avg(<parameter>)`

## Parámetros

Tipos compatibles:

* listInteger
* listDecimal
* decimal
* integer

## Firmas y tipo devuelto

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Devuelve un decimal.

## Ejemplos

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Devuelve 7.0.

`avg(10.2, 3)`

Devuelve 6.6.
