---
title: getBestSendTime
description: Obtenga información sobre la función getBestSendTime
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


# getBestSendTime {#getBestSendTime}

Proporciona un tiempo de predicción del mejor momento para enviar un correo electrónico a un individuo.

Esta función utiliza una puntuación calculada en la Plataforma. La puntuación calcula la tendencia a hacer clic o abrir un correo electrónico en el futuro en función del comportamiento anterior. Tenga en cuenta que el algoritmo que calcula la puntuación necesita una cierta cantidad de datos para funcionar. Como resultado, cuando no tiene suficientes datos, se aplicará la hora predeterminada. For more information, see [](../building-journeys/wait-activity.md).

Para utilizar esta función, se necesita un [espacio de nombres](../event/selecting-the-namespace.md) .

>[!NOTE]
>
>Tenga en cuenta que la mejor puntuación de tiempo de envío puede no estar disponible si no hay datos suficientes para realizar el cálculo. En este caso, se le informará, en el momento de la publicación, de que se aplica la hora predeterminada.

## Categoría

Adobe Experience Platform

## Sintaxis de función

`getBestSendTime(<parameters>)`

## Parámetros

| Parámetro | Descripción | Tipo |
|--- |--- |--- |
| cantidad de tiempo | Número de horas que se deben tener en cuenta desde el momento actual (máximo: 168) para optimizar el envío de correo electrónico | `<integer>` |
| tipo de optimización | &quot;open&quot; o &quot;click&quot; | `<string>` |
| tiempo predeterminado en horas de espera | En caso de que las puntuaciones de tiempo de envío predictivas no estén disponibles | `<integer>` |

## Firma y tipo devuelto

`getBestSendTime(<integer>,<string>,<integer>)`

Devuelve un valor de dateTime.

## Ejemplo

getBestSendTime(12,&quot;open&quot;,8)

Explicación:

La función devolverá el mejor momento para enviar un mensaje en las próximas 12 horas, con el fin de optimizar la probabilidad de que el individuo en la instancia del viaje lo abra. En caso de que no haya datos suficientes para realizar el cálculo, el tiempo devuelto será de 8 horas a partir del tiempo actual.
