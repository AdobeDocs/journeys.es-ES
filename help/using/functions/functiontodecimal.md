---
product: adobe campaign
title: toDecimal
description: Obtenga información sobre la función aDecimal
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 9%

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
