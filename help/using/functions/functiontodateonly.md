---
product: adobe campaign
title: toDateOnly
description: Obtenga información sobre la función toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

Convierte un valor de argumento en un valor de solo fecha.

## Categoría

Conversión

## Sintaxis de función

`toDateOnly(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha en formato ISO-8601 o &quot;AAAA-MM-DD&quot; (formato de fecha XDM) | string |
| date | date |

## Firmas y tipos devueltos

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Devolver una fecha y hora sin considerar la zona horaria.

## Ejemplos

`toDateOnly("2016-08-18")`

devuelve un objeto dateOnly que representa 2016-08-18.
