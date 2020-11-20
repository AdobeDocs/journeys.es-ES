---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: Obtenga información sobre la clasificación de funciones
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%

---


# sort {#sort}

Ordena una lista de valores en el orden natural. El primer argumento es la lista de valores, el segundo es un valor booleano que indica si la ordenación es ascendente (true) o descendente (false).

## Categoría

Lista

## Sintaxis de función

`sort(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Booleano | Booleano |

## Firma y tipo devuelto

`sort(<listInteger>,<boolean>)`

Devuelve una lista de enteros.

`sort(<listDecimal>,<boolean>)`

Devuelve una lista de decimales.

`sort(<listString>,<boolean>)`

Devuelve una lista de cadenas.

`sort(<listDateTimeOnly>,<boolean>)`

Devuelve una lista de datetimes sin tener en cuenta la zona horaria.

`sort(<listDateTime>,<boolean>)`

Devuelve una lista de datetimes.

`sort(<listBoolean>,<boolean>)`

Devuelve una lista de booleanos.

## Ejemplo

`sort(["A", "C", "B"], true)`

Devuelve `["A","B","C"]`.

`sort([1, 3, 2], false)`

Devuelve `[3, 2, 1]`.
