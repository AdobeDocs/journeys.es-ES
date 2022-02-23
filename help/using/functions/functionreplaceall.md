---
product: adobe campaign
title: replaceAll
description: Obtenga información sobre la función replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 10%

---

# replaceAll {#replaceAll}

Reemplaza todas las ocurrencias que coinciden con la cadena de destino por la cadena de reemplazo en la cadena base.

La sustitución procede desde el principio de la cadena hasta el final, por ejemplo, reemplazar &quot;aa&quot; por &quot;b&quot; en la cadena &quot;aaa&quot; resultará en &quot;ba&quot; en lugar de &quot;ab&quot;.

## Categoría

Cadena

## Sintaxis de función

`replaceAll(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|--------------|
| base | string |
| Target | string (RegExp) |
| reemplazo | string |

## Firma y tipo devuelto

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Devuelve una cadena.

## Ejemplo{#example}

`replaceAll("Hello World", "l", "x")`

Devuelve &quot;Hexxo Worxd&quot;.

Como el parámetro de destino es un RegExp, según la cadena que desee reemplazar, es posible que tenga que escapar algunos caracteres. Consulte el ejemplo en [esta página](../functions/functionreplace.md#example_2).
