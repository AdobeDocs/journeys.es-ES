---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: Obtenga información sobre la función en LastYears
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

---


# inLastYears {#inLastYears}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora: años delta.

## Categoría

Fecha

## Sintaxis de función

`inLastYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Devuelve verdadero.
