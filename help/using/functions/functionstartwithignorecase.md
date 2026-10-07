---
product: adobe campaign
title: startWithIgnoreCase
description: Obtenga información sobre la función startWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 25%
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
| cadena | cadena |
| prefijo | cadena |

## Firma y tipo devuelto

`startWithIgnoreCase(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`startWithIgnoreCase("rowing is great", "RO")`

Devuelve verdadero.
