---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Obtenga información sobre la función toDecimal
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

---


# toDecimal {#toDecimal}

Convierte un valor de argumento en un valor decimal, según su tipo.

## Categoría

Conversión

## Sintaxis de función

`toDecimal(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| string | convierte el valor de cadena como decimal |
| dateTime | convierte la fecha como el número de milisegundos (epoch milisegundos) |
| booleano | convierte el valor booleano como 1 si es true, 0 si es false |
| integer | se convierte en un decimal (ejemplo.:: 1 pasa a ser 1.0) |

## Firmas y tipos devueltos

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Devuelve un decimal.

## Ejemplos

`toDecimal("4.0")`

Devuelve 4.0.
