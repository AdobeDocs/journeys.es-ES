---
product: adobe campaign
title: distinctCount
description: Obtenga información sobre la función distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCount{#distinctCount}

Cuenta el número de valores diferentes que ignoran los valores nulos.

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

## Firma y tipo devuelto

`distinctCount(<listAny>)`

Devuelve un número entero.

## Ejemplo

`distinctCount([10,2,10,null])`

Devuelve 2.
