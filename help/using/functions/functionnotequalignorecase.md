---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Obtenga información sobre la función notEqualWithIgnoreCase
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Compruebe si la primera cadena de argumento con la segunda cadena de argumento es diferente, ignorando las consideraciones de mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`notEqualWithIgnoreCase(<parameters>)`

## Parámetros

* string

## Firma y tipo devuelto

`notEqualWithIgnoreCase(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
