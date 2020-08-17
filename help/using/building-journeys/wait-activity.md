---
title: Actividad de espera
description: Obtenga información sobre la actividad de espera
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
source-git-commit: 92bd110c4c91c459c8074184bdb486733ab5f3d7
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 2%

---


# Actividad de espera{#section_rlm_nft_dgb}

Si desea esperar antes de ejecutar la siguiente actividad en la ruta, puede utilizar una **[!UICONTROL Wait]** actividad. Permite definir el momento en que se ejecutará la siguiente actividad. Hay cuatro opciones disponibles:

* [Duración](#duration)
* [Fecha fija](#fixed_date)
* [Personalizado](#custom)
* [Optimización del tiempo de envío por correo electrónico](#email_send_time_optimization)

## Acerca de la actividad de espera{#about_wait}

Así es como se priorizan las esperas cuando se utilizan varias esperas en paralelo. Si tienen la misma configuración de tiempo y una condición diferente pero superpuesta, la espera colocada arriba será la que tenga prioridad. Por ejemplo, la condición de la primera espera es &quot;ser mujer&quot; y la condición de la segunda espera paralela es &quot;ser un VIP&quot;. Se asignará prioridad a la primera actividad de espera

También tenga en cuenta que si hay dos esperas diferentes en paralelo, se dará prioridad a la que se produzca primero, independientemente de su posición vertical. Por ejemplo, si se supera una espera de 1 hora y se supera una espera de 30 minutos, después de 30 minutos se procesará la espera de 30 minutos.

Puede definir una condición si desea restringir la espera a una determinada población.

>[!NOTE]
>
>La duración máxima de espera es de 30 días.
>
>En el modo de prueba, el **[!UICONTROL Wait time in test]** parámetro le permite definir el tiempo que durará cada actividad de espera. El valor del tiempo predeterminado es de 10 segundos. Esto garantizará que los resultados de la prueba se obtengan rápidamente. Consulte [](../building-journeys/testing-the-journey.md)

## Duración de espera{#duration}

Seleccione la duración de la espera antes de la ejecución de la siguiente actividad.

![](../assets/journey55.png)

## Espera de fecha fija{#fixed_date}

Seleccione la fecha de ejecución de la siguiente actividad.

![](../assets/journey56.png)

## Espera personalizada{#custom}

Esta opción le permite definir una fecha personalizada, por ejemplo, el 12 de julio de 2020 a las 17.00 horas, mediante una expresión avanzada basada en un campo procedente de un evento o de un origen de datos. No permite definir una duración personalizada, por ejemplo, 7 días. La expresión en el editor de expresiones debe proporcionar un formato dateTimeOnly. Consulte [](../expression/expressionadvanced.md). Para obtener más información sobre el formato dateTimeOnly, consulte [](../expression/data-types.md).

>[!NOTE]
>
>Puede aprovechar una expresión dateTimeOnly o utilizar una función para convertir a dateTimeOnly. Por ejemplo: toDateTimeOnly(@{Evento.offerOpened.actividad.endTime}), siendo el campo del evento el formulario 2016-08-12T09:46:06.
>
>El **huso** horario se espera en las propiedades del viaje. Como resultado, hoy no es posible desde la interfaz apuntar directamente a una marca de tiempo ISO-8601 completa, mezclando el tiempo y el huso horario como 2016-08-12T09:46:06.982-05. Consulte [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Optimización del tiempo de envío por correo electrónico{#email_send_time_optimization}

>[!CAUTION]
>
>La capacidad de optimización del tiempo de envío de correo electrónico solo está disponible para los clientes que utilizan el conector [de datos de](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html)Adobe Experience Platform.

Este tipo de espera utiliza una puntuación calculada en el Adobe Experience Platform. La puntuación calcula la tendencia a hacer clic o abrir un correo electrónico en el futuro en función del comportamiento anterior. Tenga en cuenta que el algoritmo que calcula la puntuación necesita una cierta cantidad de datos para funcionar. Como resultado, cuando no tiene datos suficientes, se aplicará el tiempo de espera predeterminado. En el momento de la publicación, se le notificará que se aplica la hora predeterminada.

>[!NOTE]
>
>El primer evento de tu viaje debe tener una Área de nombres.
>
>Esta capacidad solo está disponible después de una **[!UICONTROL Email]** actividad. Necesitas tener Adobe Campaign Standard.

1. En el **[!UICONTROL Amount of time]** campo, defina el número de horas que se deben considerar para optimizar el envío de correo electrónico.
1. En el **[!UICONTROL Optimization type]** campo, elija si la optimización debe aumentar los clics o abrir.
1. En el **[!UICONTROL Default time]** campo, defina el tiempo predeterminado de espera si la puntuación de tiempo de envío predictiva no está disponible.

   >[!NOTE]
   >
   >Tenga en cuenta que la puntuación de tiempo de envío puede no estar disponible porque no hay datos suficientes para realizar el cálculo. En este caso, se le informará, en el momento de la publicación, de que se aplica la hora predeterminada.

![](../assets/journey57bis.png)
