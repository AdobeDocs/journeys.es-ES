---
product: adobe campaign
title: inNextHours
description: Obtenga información sobre la función en NextHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextHours {#inNextHours}

Devuelve true si una fecha o dateTime determinada está entre ahora y ahora + horas delta.

## Categoría

Fecha

## Sintaxis de función

`inNextHours(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | entero |

## Firmas y tipo devuelto

`inNextHours(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Devuelve verdadero.
