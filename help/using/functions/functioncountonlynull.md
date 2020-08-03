---
title: countOnlyNull
description: Obtenga información sobre la función countOnlyNull
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 26%

---


# countOnlyNull {#countOnlyNull}

Cuenta el número de valores nulos de la lista.

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

Devuelve un entero.

## Ejemplo

`count([10,2,10,null])`

Devuelve 1.
