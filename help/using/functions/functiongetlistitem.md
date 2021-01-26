---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Obtenga información sobre la función gstListItem
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 11%

---


# getListItem {#gestListItem}

Devuelve el elemento de la lista en el índice dado.

## Categoría

Lista

## Sintaxis de función

`getListItem(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| lista | listString |
| lista | listBoolean |
| lista | listInteger |
| lista | listDecimal |
| lista | listDuration |
| lista | listDateTime |
| lista | listDateTimeOnly |
| index | integer |

## Firmas y tipo devuelto

`getListItem(<listInteger>,<index>)`

Devuelve una lista de enteros.

`getListItem(<listDecimal>,<index>)`

Devuelve una lista de decimales.

`getListItem(<listString>,<index>)`

Devuelve una lista de cadenas.

`getListItem(<listDateTimeOnly>,<index>)`

Devuelve una lista de datetimes sin tener en cuenta la zona horaria.

`getListItem(<listDateTime>,<index>)`

Devuelve una lista de datetimes.

`getListItem(<listBoolean>,<index>)`

Devuelve una lista de booleanos.

`getListItem(<listDuration>,<index>)`

Devuelve una lista de duraciones.

## Ejemplo

`getListItem([10, 2, 3], 1)`

Devuelve &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Devuelve &quot;C&quot;

Ejemplos con un campo de evento &#39;evento.appVersion&#39; con valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devuelve `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Devuelve &quot;20&quot;