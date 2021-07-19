---
product: adobe campaign
title: substr
description: Obtenga información sobre el substr de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 16%

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
