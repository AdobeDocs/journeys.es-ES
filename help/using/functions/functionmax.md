---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Obtenga información sobre la función max
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---

# max{#max}

Devuelve el valor máximo entre un conjunto de expresiones, dadas como una lista o dos expresiones. Se omiten los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`max(<parameter>)`

## Parámetros

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duration
* integer
* decimal
* dateTime
* dateTimeOnly

## Firmas y tipos devueltos

`max(<listDuration>)`

Devuelve una duración.

`max(<listInteger>)`

Devuelve una duración.

`max(<listDateTimeOnly>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

`max(<listDateTime>)`

Devuelve una fecha y hora.

`max(<listDecimal>)`

Devuelve un decimal.

`max(<decimal>,<decimal>)`

Devuelve un decimal.

`max(<duration>,<duration>)`

Devuelve una duración.

`max(<dateTime>,<dateTime>)`

Devuelve una fecha y hora.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

`max(<integer>,<integer>)`

Devuelve un número entero.

## Ejemplos

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Devuelve 10.

`max([10,null,8])`

Devuelve 10.
