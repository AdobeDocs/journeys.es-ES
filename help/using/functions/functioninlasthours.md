---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: Obtenga información sobre la función en LastHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 11%

---


# inLastHours {#inLastHours}

Devuelve verdadero si la fecha y hora dada está entre ahora y ahora - horas delta.

## Categoría

Fecha

## Sintaxis de función

`inLastHours(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inLastHours(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Devuelve true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Devuelve true.
