---
product: adobe campaign
title: distinct
description: Obtenga información acerca de la función distinct
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 6%

---

# distinct {#distinct}

Devuelve los distintos valores u objetos de una lista determinada. Las entradas nulas se omiten.

## Categoría

Lista

## Sintaxis de función

`distinct(<parameters>)`

## Parámetros

| Parámetro | Tipo | Descripción |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Lista para procesar. Para listObject, debe ser una referencia de campo. |
| keyAttributeName | cadena | Este parámetro es opcional y solo para listObject. Si no se proporciona el parámetro, un objeto se considera duplicado si todos los atributos tienen los mismos valores. De lo contrario, un objeto se considera duplicado si el atributo dado tiene el mismo valor. |

## Firmas y tipos devueltos

`distinct(<listInteger>)`

Devuelve una lista de enteros.

`distinct(<listDecimal>)`

Devuelve una lista de decimales.

`distinct(<listString>)`

Devuelve una lista de cadenas.

`distinct(<listDateTimeOnly>)`

Devuelve una lista de horas de fecha sin tener en cuenta la zona horaria.

`distinct(<listDateTime>)`

Devuelve una lista de fechas y horas.

`distinct(<listDateOnly>)`

Devuelve una lista de fechas.

`distinct(<listBoolean>)`

Devuelve una lista de valores booleanos.

`distinct(<listDuration>)`

Devuelve una lista de duraciones.

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

Devuelve una lista de objetos.


## Ejemplos

`distinct([10,2,10,null])`

Devuelve `[10, 2]`.
