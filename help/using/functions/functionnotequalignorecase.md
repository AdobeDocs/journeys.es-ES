---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Obtenga información sobre la función notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Compruebe si la primera cadena de argumento con la segunda cadena de argumento es diferente, omitiendo las consideraciones de mayúsculas y minúsculas.

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
