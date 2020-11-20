---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Obtenga información sobre la función endWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 11%

---


# endWith {#endWith}

Devuelve true si el segundo parámetro es un sufijo del primero.

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

Devuelve true.

`endWith("Hello World", "Hello")`

Devuelve false.
