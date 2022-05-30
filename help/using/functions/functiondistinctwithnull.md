---
product: adobe campaign
title: distinctWithNull
description: Obtenga información sobre la función distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 5%

---

# distinctWithNull {#distinctWithNull}

Devuelve los valores u objetos distintos de una lista determinada. Si la lista tiene al menos una entrada nula, estará presente una entrada nula en la lista devuelta.

## Categoría

Lista

## Sintaxis de función

`distinctWithNull(<parameters>)`

## Parámetros

| Parámetro | Tipo | Descripción |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Lista para procesar. Para listObject, debe ser una referencia de campo. |
| keyAttributeName | string | Este parámetro es opcional y solo para listObject. Si no se proporciona el parámetro, un objeto se considera duplicado si todos los atributos tienen los mismos valores. De lo contrario, un objeto se considera duplicado si el atributo dado tiene el mismo valor. |

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

`distinctWithNull(<listDateOnly>)`

Devuelve una lista de fechas.

`distinctWithNull(<listBoolean>)`

Devuelve una lista de booleanos.

`distinctWithNull(<listDuration>)`

Devuelve una lista de duraciones.

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

Devuelve una lista de objetos.

## Ejemplos

`distinctWithNull([10,2,10,null])`

Devuelve [10, 2, nulo]
