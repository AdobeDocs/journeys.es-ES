---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: Obtenga información sobre la función replaceAll
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---


# replaceAll {#replaceAll}

Reemplaza todas las incidencias que coinciden con la cadena de destinatario por la cadena de reemplazo en la cadena base.

El reemplazo procede desde el principio de la cadena hasta el final, por ejemplo, reemplazar &quot;aa&quot; por &quot;b&quot; en la cadena &quot;aaa&quot; resultará en &quot;ba&quot; en lugar de &quot;ab&quot;.

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
