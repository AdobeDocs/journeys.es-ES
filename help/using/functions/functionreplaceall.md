---
product: adobe campaign
title: replaceAll
description: Obtenga información sobre la función replaceAll
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
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
| target | string |
| reemplazo | string |

## Firma y tipo devuelto

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Devuelve una cadena.

## Ejemplo

`replaceAll("Hello World", "l", "x")`

Devuelve &quot;Hexxo Worxd&quot;.
