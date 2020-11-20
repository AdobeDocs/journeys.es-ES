---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Obtenga información sobre la función startWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 11%

---


# startWith {#startWith}

Devuelve true si el segundo parámetro es un prefijo del primero.

## Categoría

Cadena

## Sintaxis de función

`startWith(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-------------|--------|
| string | string |
| prefix | string |

## Firma y tipo devuelto

`startWith(<string>,<string>)`

Devolver un booleano.

## Ejemplo

`startWith("Hello World", "Hello")`

Devuelve true.

`startWith("Hello World", "World")`

Devuelve false.
