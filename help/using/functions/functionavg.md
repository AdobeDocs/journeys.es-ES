---
product: adobe campaign
title: avg
description: Obtenga información sobre la función avg
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 14%

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
