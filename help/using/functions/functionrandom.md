---
product: adobe campaign
title: random
description: Obtenga información sobre la función aleatoria
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

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

Explicación: si la proporción de éxito no tiene valor/es nulo, se aplicará el valor predeterminado y será una cifra aleatoria entre 0 y 1 * 100 (es decir, entre 0 y 100).
