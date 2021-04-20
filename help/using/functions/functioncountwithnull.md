---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Obtenga información sobre la función countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%

---


# countWithNull {#countWithNull}

Cuenta todos los elementos de la lista, incluidos los valores nulos.

## Categoría

Agregación

## Sintaxis de función

`countWithNull(<listAny>)`

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

## Firma y tipo devuelto

`countWithNull(<listAny>)`

Devuelve un número entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 4.
