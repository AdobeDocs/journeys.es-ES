---
title: avg
description: Obtenga información sobre la función avg
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---


# avg {#avg}

Devuelve el valor promedio entre un conjunto de expresiones, dado como una lista o como dos expresiones. Se omiten los valores nulos.


## Categoría

Agregación

## Sintaxis de función

`avg(<parameter>)`

## Parámetros

Tipos admitidos:

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
