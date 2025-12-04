---
product: adobe campaign
title: distinctCount
description: Obtenga información sobre la función distinctCount
feature: Journeys
role: Developer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCount{#distinctCount}

Cuenta el número de valores diferentes e ignora los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`distinctCount(<listAny>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Firma y tipo devuelto

`distinctCount(<listAny>)`

Devuelve un entero.

## Ejemplo

`distinctCount([10,2,10,null])`

Devuelve 2.
