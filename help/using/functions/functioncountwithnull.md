---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Obtenga información sobre la función countWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
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

Devuelve un entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 4.
