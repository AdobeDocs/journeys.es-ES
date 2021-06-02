---
product: adobe campaign
title: toInteger
description: Obtenga información sobre la función toInteger
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 9%

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
| string | convierte el valor de cadena en un entero |
| dateTime | convierte la fecha en el número de milisegundos (epoch miliseconds) |
| decimal | se convierte en entero eliminando la parte decimal (ejemplo: 1,5 se convierte en 1) |
| booleano | convierte el valor booleano en 1 si es verdadero, 0 si es falso |

## Firmas y tipo devuelto

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Devuelve un entero.

## Ejemplos

`toInteger("4")`

Devuelve 4.
