---
product: adobe campaign
title: toBool
description: Obtenga información sobre la función aBool
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%

---

# toBool {#toBool}

Convierte un valor de argumento en un valor booleano, según su tipo.

* De cadena: intente convertir el valor de cadena como booleano, de &quot;true&quot; si el valor de cadena es &quot;true&quot;, en &quot;false&quot; en caso contrario
* De cifras: true si el valor numérico no es igual a 0, false en caso contrario

## Categoría

Conversión

## Sintaxis de función

`toBool(<parameter>)`

## Parámetros

* decimal
* Booleano
* string
* entero

## Firmas y tipos devueltos

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Devuelve un booleano.

## Ejemplos

`toBool("true")`

`toBool(1)`

Devuelve verdadero.

`toBool("this is not a boolean")`

Devuelve falso.
