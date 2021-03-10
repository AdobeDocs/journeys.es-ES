---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Obtenga información sobre la división de funciones
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 8%

---


# split {#split}

Divide la primera cadena de argumento con una cadena separador (la segunda cadena de argumento, que puede ser una expresión regular) para generar una lista de cadenas (tokens).

## Categoría

Cadena

## Sintaxis de función

`split(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| cadena de entrada | string |
| cadena de separador | string |

## Firmas y tipo devuelto

`split(<input string>, <separator string>)`

Devuelve un listString.

## Ejemplo

`split(["A_B_C"], "_")`

Devuelve `["A","B","C"]`

Ejemplo con un campo de evento &quot;event.appVersion&quot; con valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devuelve `["20", "45", "2", "3434"]`
