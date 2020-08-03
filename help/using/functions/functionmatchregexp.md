---
title: matchRegExp
description: Obtenga información sobre la función matchRegExp
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
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
