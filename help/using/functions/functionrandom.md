---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Obtenga información sobre la función aleatoria
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
