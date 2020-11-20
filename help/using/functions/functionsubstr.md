---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: Obtenga información sobre el substor de funciones
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 6%

---


# substr {#substr}

Devuelve la subcadena de la expresión de cadena entre el índice de inicio y el índice final. Si el índice final no está definido, se encuentra entre el índice inicial y el final.

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

Devuelve &quot;World&quot;.

`substr("Hello World", 0, 5)`

Devuelve &quot;Hello&quot;.