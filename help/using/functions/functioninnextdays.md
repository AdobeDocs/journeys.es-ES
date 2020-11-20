---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: Obtenga información sobre la función en NextDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inNextDays {#inNextDays}

Devuelve true si una fecha o fechaTime dada está entre ahora y ahora + días delta.

## Categoría

Fecha

## Sintaxis de función

`inNextDays(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inNextDays(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Devuelve true.
