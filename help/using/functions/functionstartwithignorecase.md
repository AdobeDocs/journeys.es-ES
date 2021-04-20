---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: Obtenga información sobre la función startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

---


# startWithIgnoreCase {#startWithIgnoreCase}

Devuelve true si el segundo parámetro es un prefijo del primero sin tener en cuenta las mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`startWithIgnoreCase(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-------------|--------|
| string | string |
| prefix | string |

## Firma y tipo devuelto

`startWithIgnoreCase(<string>,<string>)`

Devuelve un booleano.

## Ejemplo

`startWith("rowing is great', "RO")`

Devuelve verdadero.
