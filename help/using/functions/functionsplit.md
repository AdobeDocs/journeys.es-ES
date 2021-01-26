---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Obtenga información sobre la división de funciones
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 6%

---


# split {#split}

Divide la primera cadena de argumento con una cadena separadora (la segunda cadena de argumento, que puede ser una expresión normal) para generar una lista de cadenas (tokens).

## Categoría

Cadena

## Sintaxis de función

`split(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| cadena de entrada | string |
| cadena separador | string |

## Firmas y tipo devuelto

`split(<input string>, <separator string>)`

Devuelve un valor de listString.

## Ejemplo

`split(["A_B_C"], "_")`

Devuelve `["A","B","C"]`

Ejemplo con un campo de evento &#39;evento.appVersion&#39; con valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devuelve `["20", "45", "2", "3434"]`
