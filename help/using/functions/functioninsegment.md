---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Obtenga información sobre la función enSegment
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 7%

---


# inSegment {#inSegment}

Comprueba si un individuo pertenece a un segmento determinado.

El nombre del segmento debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión.

Los segmentos se definen en el [Adobe Experience Platform](https://platform.adobe.com/segment/overview). El editor de expresiones proporciona una lista de segmentos completada automáticamente.

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

La función regresará **[!UICONTROL true]** si el individuo dentro de la instancia de viaje es parte del segmento de Adobe Experience Platform llamado &quot;hombres mayores de 50&quot;, de lo contrario **[!UICONTROL false]** .
