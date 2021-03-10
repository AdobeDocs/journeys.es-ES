---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: Obtenga información sobre la función en NextMonths
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

---


# inNextMonths {#inNextMonths}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora + meses delta.

## Categoría

Fecha

## Sintaxis de función

`inNextMonths(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inNextMonths(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Devuelve verdadero.
