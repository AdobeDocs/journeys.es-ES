---
product: adobe campaign
title: count
description: Obtenga información sobre el recuento de funciones
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 27%

---

# count {#count}

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

## Firmas y tipo devuelto

`count(<listAny>)`

Devuelve un número entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 3.
