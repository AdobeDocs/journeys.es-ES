---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Obtenga información sobre el administrador de funciones
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---


# min {#min}

Devuelve el valor mínimo entre un conjunto de expresiones, dado como una lista o dos expresiones. Se omiten los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`min(<parameters>)`

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

`min(<listDuration>)`

Devuelve una duración.

`min(<listInteger>)`

Devuelve una duración.

`min(<listDateTimeOnly>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

`min(<listDateTime>)`

Devuelve una fecha y hora.

`min(<listDecimal>)`

Devuelve un decimal.

`min(<decimal>,<decimal>)`

Devuelve un decimal.

`min(<duration>,<duration>)`

Devuelve una duración.

`min(<dateTime>,<dateTime>)`

Devuelve una fecha y hora.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Devuelve una fecha y hora sin tener en cuenta la zona horaria.

`min(<integer>,<integer>)`

Devuelve un entero.

## Ejemplos

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Devuelve 3.

`min([10,null,8])`

Devuelve 8.
