---
product: adobe campaign
title: inSegment
description: Obtenga información sobre la función en Segment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 8%

---

# inSegment {#inSegment}

Comprueba si una persona pertenece a un segmento determinado.

>[!NOTE]
>
>Puede recuperar hasta 100 segmentos.

El nombre del segmento debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión.

Los segmentos se definen en [Adobe Experience Platform](https://platform.adobe.com/segment/overview). El editor de expresiones proporciona una lista de segmentos autocompletada.

>[!NOTE]
>
>Solo las personas con los estados de participación de segmentos **Realized** y **Existing** se considerarán miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [Documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

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
