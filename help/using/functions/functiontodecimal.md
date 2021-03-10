---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Obtenga información sobre la función aDecimal
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

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
| string | convierte el valor de cadena en decimal |
| dateTime | convierte la fecha en el número de milisegundos (epoch miliseconds) |
| booleano | convierte el valor booleano en 1 si es verdadero, 0 si es falso |
| integer | se convierte en decimal (ejemplo.: 1 se convierte en 1.0) |

## Firmas y tipos devueltos

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Devuelve un decimal.

## Ejemplos

`toDecimal("4.0")`

Devuelve 4.0.
