---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: Obtenga información sobre la función distinctCount
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%

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
