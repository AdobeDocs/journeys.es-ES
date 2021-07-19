---
product: adobe campaign
title: serializeList
description: Obtenga información sobre la función serializeList
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 20%

---

# serializeList {#serializeList}

Convierte la lista (cualquier tipo) proporcionada en el primer parámetro en una cadena. El segundo parámetro representa el separador que se va a utilizar. El tercer parámetro es un valor booleano que indica si cada elemento de la expresión debe incluir comillas.

## Categoría

Lista

## Sintaxis de función

`serializeList(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| Cadena | Cadena |
| Booleano | Booleano |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listPoint |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Firma y tipo devuelto

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Devuelve una cadena.

## Ejemplo

`serializeList(["Hello","World"], " ", false)`

Devuelve &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Devuelve &quot;Hello&quot;, &quot;World&quot;.
