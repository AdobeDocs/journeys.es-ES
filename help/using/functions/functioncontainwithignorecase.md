---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Obtenga información sobre la función containWithIgnoreCase
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Comprueba si la segunda cadena de argumento está contenida en la primera cadena de argumento, sin tener en cuenta las mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`containWithIgnoreCase(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| string | string |
| cadena buscada | string |

## Firma y tipo devuelto

`containWithIgnoreCase(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`containWithIgnoreCase("rowing is great', "GREAT")`

Devuelve verdadero.
