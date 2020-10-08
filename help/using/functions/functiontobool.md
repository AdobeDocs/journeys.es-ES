---
title: toBool
description: Obtenga información sobre la función toBool
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

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
