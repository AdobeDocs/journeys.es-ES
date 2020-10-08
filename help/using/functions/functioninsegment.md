---
title: inSegment
description: Obtenga información sobre la función enSegment
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
