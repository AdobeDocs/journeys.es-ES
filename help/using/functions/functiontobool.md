---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Obtenga información sobre la función aBool
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

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
* booleano
* string
* integer

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
