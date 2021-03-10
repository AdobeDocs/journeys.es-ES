---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Obtenga información sobre la función en Segment
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 8%

---


# inSegment {#inSegment}

Comprueba si una persona pertenece a un segmento determinado.

El nombre del segmento debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión.

Los segmentos se definen en [Adobe Experience Platform](https://platform.adobe.com/segment/overview). El editor de expresiones proporciona una lista de segmentos autocompletada.

>[!NOTE]
>
>Puede recuperar hasta 100 segmentos.

## Categoría

Adobe Experience Platform

## Sintaxis de función

`inSegment(<parameter>)`

## Parámetros

| Parámetro | Descripción | Tipo |
|--- |--- |--- |
| Segmento | El nombre del segmento | `<string>` |

## Firma y tipo devuelto

`inSegment(<string>)`

Devuelve un valor booleano.

## Ejemplo

`inSegment("men over 50")`

Explicación:

La función devolverá **[!UICONTROL true]** si el individuo dentro de la instancia de recorrido forma parte del segmento de Adobe Experience Platform llamado &quot;hombres mayores de 50&quot;, **[!UICONTROL false]** en caso contrario.
