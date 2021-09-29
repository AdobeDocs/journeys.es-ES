---
product: adobe campaign
title: filter
description: Obtenga información sobre el fister de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

Devuelve un listObject con objetos cuyo atributo clave coincida con uno de los valores de clave determinados.

## Categoría

Lista

## Sintaxis de función

`filter(<parameters>)`

## Parámetros

| Parámetro | Tipo | Descripción |
|-----------|------------------|------------------|
| listToFilter | listObject | lista de objetos que se van a filtrar. Debe ser una referencia de campo. |
| keyAttributeName | string | nombre de atributo en los objetos de la lista dada, utilizado como clave para filtrar |
| keyValueList | list | matriz de valores clave para filtrar |

## Firmas y tipos devueltos

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Devuelve un listObject.

## Ejemplos

Este es un ejemplo de carga útil que se pasa en un evento entrante &quot;myevent&quot;:

```
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Puede utilizar la siguiente expresión:

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

Devuelve un listObject que contiene los dos objetos con &quot;product2&quot; y &quot;product3&quot; como id.
