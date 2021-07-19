---
product: adobe campaign
title: containWithIgnoreCase
description: Obtenga información sobre la función containWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

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
