---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Obtenga información sobre la función aleatoria
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
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

Explicación: si la proporción de éxito no tiene valor/es nulo, se aplicará el valor predeterminado y será una cifra aleatoria entre 0 y 1 * 100 (es decir, entre 0 y 100).
