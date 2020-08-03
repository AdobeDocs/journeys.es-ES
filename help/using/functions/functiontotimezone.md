---
title: toTimeZone
description: Obtenga información sobre la función toTimeZone
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# toTimeZone {#toTimeZone}

Convierte un valor de cadena en una zona horaria.

## Categoría

Conversión

## Sintaxis de función

`toTimeZone(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| string | El valor de cadena debe contener la identificación de zona. Puede ser una referencia de campo o una expresión |

## Firmas y tipos devueltos

`toTimeZone(<string>)`

Devuelve un huso horario.

## Ejemplos

`toTimeZone("UTC")`

Devuelve UTC.
