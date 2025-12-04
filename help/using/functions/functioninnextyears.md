---
product: adobe campaign
title: inNextYears
description: Obtenga información sobre la función en NextYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextYears {#inNextYears}

Devuelve true si una fecha o dateTime determinada está entre ahora y ahora + años delta.

## Categoría

Fecha

## Sintaxis de función

`inNextYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | entero |

## Firmas y tipo devuelto

`inNextYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Devuelve verdadero.
