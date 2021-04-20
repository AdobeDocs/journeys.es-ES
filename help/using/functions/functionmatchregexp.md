---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Obtenga información sobre la función matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 6%

---


# matchRegExp {#matchRegExp}

Devuelve true si la cadena del primer parámetro coincide con la expresión regular del segundo parámetro. Para obtener más información, consulte [esta página](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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

Devuelve un valor verdadero.

## Ejemplo

`matchRegExp("Hello World", "Hello\s+World")`

Devuelve verdadero.

Explicación:

Aquí puede comprobar si la cadena cumple la expresión regular (sintaxis java): comienza con &quot;Hello&quot;, luego cualquier tipo de cadena y termina con &quot;World&quot;.
