---
product: adobe campaign
title: inSegment
description: Obtenga información sobre la función en Segmento
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 6%

---

# inSegment {#inSegment}

Comprueba si un individuo pertenece a un segmento determinado.

>[!NOTE]
>
>Puede recuperar hasta 100 segmentos.

El nombre del segmento debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión.

Los segmentos se definen en [Adobe Experience Platform](https://platform.adobe.com/segment/overview). El editor de expresiones proporciona una lista autocompletada de segmentos.

Los segmentos pueden tener tres estados:

* existente: la entidad sigue estando en el segmento.
* realizado: la entidad se está introduciendo en el segmento.
* saliente: la entidad sale del segmento.

Solo las personas con los estados de participación en los segmentos **Realized** y **Existing** se considerarán como miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=es#interpret-segment-results).

`IF inSegment('segmentName') == true` significa que tiene un segmentMembership con el estado introducido/existente.

`ELSE inSegment('segmentName') == false` significa que usted tiene un segmentMembership del estado saliente.

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

La función devolverá **[!UICONTROL true]** si el individuo de la instancia de recorrido es parte del segmento de Adobe Experience Platform denominado &quot;hombres de más de 50 años&quot;, **[!UICONTROL false]** en caso contrario.
