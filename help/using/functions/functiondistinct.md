---
title: distinct
description: Obtenga información sobre la función distinta
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
