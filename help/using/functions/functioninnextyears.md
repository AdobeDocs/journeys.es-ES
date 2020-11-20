---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: Obtenga información sobre la función en NextYears
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inNextYears {#inNextYears}

Devuelve true si una fecha o fechaTime dada está entre ahora y ahora + años delta.

## Categoría

Fecha

## Sintaxis de función

`inNextYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inNextYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Devuelve true.
