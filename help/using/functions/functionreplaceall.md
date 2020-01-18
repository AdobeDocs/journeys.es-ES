---
title: replaceAll
description: Obtenga información sobre la función replaceAll
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# replaceAll {#replaceAll}

Reemplaza todas las incidencias que coinciden con la cadena de destino por la cadena de reemplazo en la cadena base.

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
