---
title: random
description: Obtenga información sobre la función aleatoria
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


# random {#random}

Genera un número aleatorio entre 0 y 1.

## Categoría

Matemáticas

## Sintaxis de función

`random(<parameters>)`

## Firma y tipo devuelto

`random()`

Devuelve un decimal.

## Ejemplo

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explicación: si el índice de éxito no tiene valor/es nulo, se aplicará el valor predeterminado y será una cifra aleatoria entre 0 y 1 * 100 (es decir, entre 0 y 100).
