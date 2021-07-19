---
product: adobe campaign
title: countOnlyNull
description: Obtenga información sobre la función countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 34%

---

# countOnlyNull {#countOnlyNull}

Cuenta el número de valores nulos en la lista.

## Categoría

Agregación

## Sintaxis de función

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Devuelve un número entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 1.
