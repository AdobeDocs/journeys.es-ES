---
product: adobe campaign
title: inNextMonths
description: Obtenga información sobre la función en NextMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

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
| delta | entero |

## Firmas y tipo devuelto

`inNextMonths(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Devuelve verdadero.
