---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: Obtenga información sobre la función distinta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 14%

---


# distinct {#distinct}

Devuelve los valores distintos de la lista sin valores nulos.

## Categoría

Lista

## Sintaxis de función

`distinct(<parameter>)`

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

## Firmas y tipos devueltos

`distinct(<listInteger>)`

Devuelve una lista de enteros.

`distinct(<listDecimal>)`

Devuelve una lista de decimales.

`distinct(<listString>)`

Devuelve una lista de cadenas.

`distinct(<listDateTimeOnly>)`

Devuelve una lista de datetimes sin tener en cuenta la zona horaria.

`distinct(<listDateTime>)`

Devuelve una lista de datetimes.

`distinct(<listBoolean>)`

Devuelve una lista de booleanos.

`distinct(<listDuration>)`

Devuelve una lista de duraciones.

## Ejemplos

`distinct([10,2,10,null])`

Devuelve `[10, 2]`.
