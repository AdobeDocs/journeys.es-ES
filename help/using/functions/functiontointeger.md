---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Obtenga información sobre la función toInteger
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

Convierte un valor de argumento en un entero.

## Categoría

Conversión

## Sintaxis de función

`toInteger(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| string | convierte el valor de cadena como un entero |
| dateTime | convierte la fecha como el número de milisegundos (epoch milisegundos) |
| decimal | convierte en entero eliminando la parte decimal (ejemplo: 1,5 se convierte en 1) |
| booleano | convierte el valor booleano como 1 si es true, 0 si es false |

## Firmas y tipo devuelto

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Devuelve un entero.

## Ejemplos

`toInteger(4)`

Devuelve 4.
