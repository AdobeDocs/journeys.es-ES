---
title: toString
description: Obtenga información sobre la función toString
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
source-wordcount: '112'
ht-degree: 4%

---


# toString {#toString}

Convierte un valor de argumento en un valor de cadena, según su tipo. For more information on data types, refer to [](../expression/data-types.md).

## Categoría

Conversión

## Sintaxis de función

`toString(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| dateTime | convierte la fecha en formato de fecha UTC |
| dateTimeOnly | convierte la fecha en formato de fecha UTC |
| duration | convertir en el número correspondiente de milisegundos como una cadena |
| zona horaria | convertir en representación de cadena de identificación de zona horaria (ID de JOD) |
| integer | se convierte en una representación de cadena del valor (1 pasa a ser &quot;1&quot;) |
| decimal | se convierte en una representación de cadena del valor (1,5 pasa a ser &quot;1,5&quot;) |
| booleano | convierta el valor booleano como &#39;true&#39; si es true, &#39;false&#39; si es false |

## Firmas y tipo devuelto

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Devuelve una cadena.

## Ejemplo

`toString(4)`

Devuelve &quot;4&quot;.
