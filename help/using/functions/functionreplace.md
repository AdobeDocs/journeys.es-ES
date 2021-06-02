---
product: adobe campaign
title: replace
description: Obtenga información sobre la sustitución de funciones
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 10%

---

# replace {#replace}

Reemplaza la primera incidencia que coincide con la cadena de destino por la cadena de reemplazo de la cadena base.

La sustitución procede desde el principio de la cadena hasta el final, por ejemplo, reemplazar &quot;aa&quot; por &quot;b&quot; en la cadena &quot;aaa&quot; resultará en &quot;ba&quot; en lugar de &quot;ab&quot;.

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
