---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Obtenga información sobre la función endWith
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 12%

---


# endWith {#endWith}

Devuelve el valor verdadero si el segundo parámetro es un sufijo del primero.

## Categoría

Cadena

## Sintaxis de función

`endWith(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| string | string |
| sufijo | string |

## Firma y tipo devuelto

`endWith(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`endWith("Hello World", "World")`

Devuelve verdadero.

`endWith("Hello World", "Hello")`

Devuelve falso.
