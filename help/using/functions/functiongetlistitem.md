---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Obtenga información sobre la función gstListItem
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 12%

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

Devuelve una lista de tiempos de datos sin tener en cuenta la zona horaria.

`getListItem(<listDateTime>,<index>)`

Devuelve una lista de tiempos de datos.

`getListItem(<listBoolean>,<index>)`

Devuelve una lista de booleanos.

`getListItem(<listDuration>,<index>)`

Devuelve una lista de duraciones.

## Ejemplo

`getListItem([10, 2, 3], 1)`

Devuelve &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Devuelve &quot;C&quot;

Ejemplos con un campo de evento &quot;event.appVersion&quot; con valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devuelve `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Devuelve &quot;20&quot;