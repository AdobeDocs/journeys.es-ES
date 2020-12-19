---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: Obtenga información sobre la función endWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# endWithIgnoreCase {#endWithIgnoreCase}

Comprueba si la primera cadena de argumento termina con una cadena específica (segunda cadena de argumento), sin tener en cuenta las mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`endWithIgnoreCase(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| string | string |
| sufijo | string |

## Firma y tipo devuelto

`endWithIgnoreCase(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`endWithIgnoreCase("rowing is great', "AT")`

Devuelve true.
