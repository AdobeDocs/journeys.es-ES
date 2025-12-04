---
product: adobe campaign
title: matchRegExp
description: Obtenga información sobre la función matchRegExp
feature: Journeys
role: Developer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# matchRegExp {#matchRegExp}

Devuelve true si la cadena del primer parámetro coincide con la expresión regular del segundo parámetro. Para obtener más información, vea [esta página](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoría

Cadena

## Sintaxis de función

`matchRegExp(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|--- |--- |
| cadena | cadena |
| regexp | cadena |

## Firma y tipo devuelto

`matchRegExp(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`matchRegExp("username@adobe.com", "*adobe")`

Devuelve verdadero.
