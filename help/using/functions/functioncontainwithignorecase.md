---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Obtenga información sobre la función containWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Comprueba si la segunda cadena de argumento está contenida en la primera cadena de argumento, sin tener en cuenta el caso.

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

Devuelve true.
