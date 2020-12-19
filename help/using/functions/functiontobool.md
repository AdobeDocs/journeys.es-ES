---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Obtenga información sobre la función toBool
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# toBool {#toBool}

Convierte un valor de argumento en un valor booleano, según su tipo.

* Desde cadena: intente convertir el valor de cadena como booleano, de &quot;true&quot; si el valor de la cadena es &quot;true&quot;, de lo contrario false
* De numérico: true si el valor numérico no es igual a 0, false en caso contrario

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

Devolver un booleano.

## Ejemplos

`toBool("true")`

`toBool(1)`

Devuelve true.

`toBool("this is not a boolean")`

Devuelve false.
