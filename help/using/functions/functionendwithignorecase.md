---
product: adobe campaign
title: endWithIgnoreCase
description: Obtenga información sobre la función endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 20%

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

Devuelve verdadero.
