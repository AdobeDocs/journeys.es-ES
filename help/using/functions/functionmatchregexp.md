---
product: adobe campaign
title: matchRegExp
description: Obtenga información sobre la función matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 12%

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

Devuelve un valor booleano.

## Ejemplo

`matchRegExp("Hello World", "Hello\s+World")`

Devuelve verdadero.

Explicación:

Aquí puede comprobar si la cadena cumple la expresión regular (sintaxis java): comienza con &quot;Hello&quot;, luego cualquier tipo de cadena y termina con &quot;World&quot;.
