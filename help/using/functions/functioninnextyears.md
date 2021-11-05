---
product: adobe campaign
title: inNextYears
description: Obtenga información sobre la función en NextYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inNextYears {#inNextYears}

Devuelve el valor verdadero si una fecha determinada o dateTime está entre ahora y ahora + años delta.

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

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Devuelve verdadero.
