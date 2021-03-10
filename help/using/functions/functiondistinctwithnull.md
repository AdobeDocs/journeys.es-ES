---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: Obtenga información sobre la función distinctWithNull
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 12%

---


# distinctWithNull {#distinctWithNull}

Devuelve los distintos valores de la lista. Si la lista tiene al menos un valor nulo, se mostrará un valor nulo en la lista devuelta.

## Categoría

Lista

## Sintaxis de función

`distinctWithNull(<parameter>)`

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

## Firmas y tipos devueltos

`distinctWithNull(<listInteger>)`

Devuelve una lista de enteros.

`distinctWithNull(<listDecimal>)`

Devuelve una lista de decimales.

`distinctWithNull(<listString>)`

Devuelve una lista de cadenas.

`distinctWithNull(<listDateTimeOnly>)`

Devuelve una lista de tiempos de datos sin tener en cuenta la zona horaria.

`distinctWithNull(<listDateTime>)`

Devuelve una lista de tiempos de datos.

`distinctWithNull(<listBoolean>)`

Devuelve una lista de booleanos.

`distinctWithNull(<listDuration>)`

Devuelve una lista de duraciones.

## Ejemplos

`distinctWithNull([10,2,10,null])`

Devuelve [10, 2, null]
