---
product: adobe campaign
title: recuento
description: Más información sobre el recuento de funciones
feature: Journeys
role: Developer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 30%

---

# recuento {#count}

Cuenta los elementos de la lista que no tienen en cuenta los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`count(<listAny>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Firmas y tipo devuelto

`count(<listAny>)`

Devuelve un entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 3.
