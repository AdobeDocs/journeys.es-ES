---
product: adobe campaign
title: distinctCountWithNull
description: Obtenga información sobre la función distinctCountWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCountWithNull {#distinctCountWithNull}

Cuenta el número de valores diferentes, incluidos los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`distinctCountWithNull(<listAny>)`

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

`distinctCountWithNull(<listAny>)`

Devuelve un entero.

## Ejemplo

`distinctCountWithNull([10,2,10,null])`

Devuelve 3.
