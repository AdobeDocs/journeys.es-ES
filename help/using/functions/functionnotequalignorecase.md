---
product: adobe campaign
title: notEqualIgnoreCase
description: Obtenga información sobre la función notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Compruebe si la cadena del primer argumento con la cadena del segundo argumento es diferente, ignorando las consideraciones de mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`notEqualIgnoreCase(<parameters>)`

## Parámetros

* cadena

## Firma y tipo devuelto

`notEqualIgnoreCase(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
