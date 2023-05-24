---
product: adobe campaign
title: límite
description: Más información sobre el límite de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: 9f5ef0497227a370e2e1f4a62450611ae2e336b9
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 9%

---

# límite {#limit}

Devuelve los primeros o últimos elementos N de una lista.

## Categoría

Lista

## Sintaxis de función

`limit(<parameters>)`

## Parámetros

| Parámetro | Tipo | Descripción |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Lista para ordenar. Para listObject, debe ser una referencia de campo. |
| numberOfItems | entero | Número de elementos que se van a devolver de la lista determinada. |
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

Devuelve una lista de valores booleanos.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Devuelve una lista de fechas.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Devuelve una lista de horas de fecha sin tener en cuenta la zona horaria.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Devuelve una lista de fechas y horas.

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
