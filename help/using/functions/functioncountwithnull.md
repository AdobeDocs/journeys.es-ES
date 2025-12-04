---
product: adobe campaign
title: countWithNull
description: Obtenga información acerca de la función countWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

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
| Lista | listDateOnly |

## Firma y tipo devuelto

`countWithNull(<listAny>)`

Devuelve un entero.

## Ejemplo

`countWithNull([10,2,10,null])`

Devuelve 4.
