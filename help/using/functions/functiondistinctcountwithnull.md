---
product: adobe campaign
title: distinctCountWithNull
description: Obtenga información sobre la función distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

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

## Firma y tipo devuelto

`distinctCountwithNull(<listAny>)`

Devuelve un número entero.

## Ejemplo

`distinctCountWithNull([10,2,10,null])`

Devuelve 3.
