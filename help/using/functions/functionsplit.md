---
product: adobe campaign
title: split
description: Obtenga información sobre la división de funciones
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 10%

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
