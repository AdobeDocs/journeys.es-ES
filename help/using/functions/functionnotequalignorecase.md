---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Obtenga información sobre la función notEqualWithIgnoreCase
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 15%

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
