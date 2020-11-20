---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Obtenga información sobre la función matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

Devuelve true si la cadena del primer parámetro coincide con la expresión normal del segundo parámetro. For more information, see [this page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoría

Cadena

## Sintaxis de función

`matchRegExp(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|--- |--- |
| string | string |
| regexp | string |

## Firma y tipo devuelto

`matchRegExp(<string>,<string>)`

Devuelve un valor true.

## Ejemplo

`matchRegExp("Hello World", "Hello\s+World")`

Devuelve true.

Explicación:

Aquí puede comprobar si la cadena cumple la expresión normal (sintaxis de java): inicios con &quot;Hola&quot;, luego cualquier tipo de cadena y termina con &quot;Mundo&quot;.
