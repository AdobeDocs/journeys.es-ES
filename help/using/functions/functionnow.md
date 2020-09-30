---
title: now
description: Obtenga información sobre la función ahora
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 70bc6653a8cdd552a0441f4b661341d3f095b112
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# now {#now}

Devuelve la fecha actual en formato de fecha y hora. For more information on data types, refer to [](../expression/data-types.md).

## Categoría

Fecha

## Sintaxis de función

`now(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| string |  |

## Firmas y tipo devuelto

`now()`

`now("<timeZone id>")`

Devuelve un valor de dateTime.

## Ejemplos

`now()`

Devuelve 2019-06-03T06:30Z.

`toString(now())`

Devuelve &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Devuelve 2019-06-03T08:30+02:00.