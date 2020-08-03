---
title: containWithIgnoreCase
description: Learn about the function containWithIgnoreCase
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
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Comprueba si la segunda cadena de argumento está contenida en la primera cadena de argumento, sin tener en cuenta el caso.

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

Devuelve true.
