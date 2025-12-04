---
product: adobe campaign
title: startWith
description: Obtenga información acerca de la función startWith
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# startWith {#startWith}

Devuelve true si el segundo parámetro es un prefijo del primero.

## Categoría

Cadena

## Sintaxis de función

`startWith(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-------------|--------|
| cadena | cadena |
| prefijo | cadena |

## Firma y tipo devuelto

`startWith(<string>,<string>)`

Devuelve un valor booleano.

## Ejemplo

`startWith("Hello World", "Hello")`

Devuelve verdadero.

`startWith("Hello World", "World")`

Devuelve falso.
