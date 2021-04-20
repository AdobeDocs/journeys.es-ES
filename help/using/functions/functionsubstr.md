---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: Obtenga información sobre el substr de funciones
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

Devuelve la subcadena de la expresión de cadena entre el índice de inicio y el índice de finalización. Si el índice final no está definido, entonces está entre el índice inicial y el final.

## Categoría

Cadena

## Sintaxis de función

`substr(<parameters>)`

## Parámetros

| Parámetro | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Firma y tipo devuelto

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Devuelve una cadena.

## Ejemplo

`substr("Hello World",6)`

Devuelve &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Devuelve &quot;Hello&quot;.