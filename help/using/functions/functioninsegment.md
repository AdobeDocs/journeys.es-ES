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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# inSegment {#inSegment}

Comprueba si un individuo pertenece a un segmento determinado.

El nombre del segmento debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión.

Los segmentos se definen en la plataforma [de](https://platform.adobe.com/segment/overview)Adobe Experience. El editor de expresiones proporciona una lista de segmentos completada automáticamente.

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

La función regresará **[!UICONTROL true]**si el individuo dentro de la instancia del viaje es parte del segmento de la plataforma llamado &quot;hombres mayores de 50&quot;, de lo contrario**[!UICONTROL false]** .
