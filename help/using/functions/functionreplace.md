---
title: reemplazar
description: Obtenga información sobre la sustitución de funciones
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# reemplazar {#replace}

Reemplaza la primera incidencia que coincide con la cadena de destino por la cadena de reemplazo en la cadena base.

El reemplazo procede desde el principio de la cadena hasta el final, por ejemplo, reemplazar &quot;aa&quot; por &quot;b&quot; en la cadena &quot;aaa&quot; resultará en &quot;ba&quot; en lugar de &quot;ab&quot;.

## Categoría

Cadena

## Sintaxis de función

`replace(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|--------------|
| base | string |
| target | string |
| reemplazo | string |

## Firma y tipo devuelto

`replace(<base>,<target>,<replacement>)`

Devuelve una cadena.

## Ejemplo

`replace("Hello World", "l", "x")`

Devuelve &quot;Hexlo World&quot;.
