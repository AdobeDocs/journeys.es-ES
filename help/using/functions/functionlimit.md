---
product: adobe campaign
title: límite
description: Obtenga información sobre el límite de funciones
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# límite {#limit}

Devuelve el primer o el último N elementos de una lista.

## Categoría

Lista

## Sintaxis de función

`limit(<parameters>)`

## Parámetros

| Parámetro | Tipo | Descripción |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Lista para ordenar. Para listObject, debe ser una referencia de campo. |
| numberOfItems | integer | Número de elementos que se van a devolver de la lista dada. |
| firstOrLastItems | Booleano | Este parámetro es opcional (true de forma predeterminada). true devuelve los primeros elementos. false devuelve los últimos elementos. |

## Firma y tipo devuelto

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Devuelve una lista de cadenas.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Devuelve una lista de enteros.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Devuelve una lista de decimales.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Devuelve una lista de booleanos.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Devuelve una lista de fechas.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Devuelve una lista de tiempos de datos sin tener en cuenta la zona horaria.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Devuelve una lista de tiempos de datos.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Devuelve una lista de duraciones.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Devuelve una lista de objetos.

## Ejemplo

`limit(["A", "B", "C", "D", "E"], 3)`

Devuelve `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Devuelve `["C","D","E"]`.
