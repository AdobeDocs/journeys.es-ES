---
product: adobe campaign
title: toInteger
description: Obtenga información acerca de la función toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

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
| cadena | convierte el valor de cadena como un entero |
| dateTime | convierte la fecha como el número de milisegundos (epoch milisegundos) |
| decimal | convierte en entero eliminando la parte decimal (ejemplo: 1,5 se convierte en 1) |
| Booleano | convierte el valor booleano como 1 si es verdadero, 0 si es falso |

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
