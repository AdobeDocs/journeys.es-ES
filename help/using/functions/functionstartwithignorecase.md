---
product: adobe campaign
title: startWithIgnoreCase
description: Obtenga información sobre la función startWithIgnoreCase
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 15%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Devuelve true si el segundo parámetro es un prefijo del primero sin tener en cuenta las mayúsculas y minúsculas.

## Categoría

Cadena

## Sintaxis de función

`startWithIgnoreCase(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-------------|--------|
| string | string |
| prefix | string |

## Firma y tipo devuelto

`startWithIgnoreCase(<string>,<string>)`

Devuelve un booleano.

## Ejemplo

`startWith("rowing is great', "RO")`

Devuelve verdadero.
