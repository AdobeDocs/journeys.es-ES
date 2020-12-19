---
product: adobe campaign
solution: Journey Orchestration
title: Actividad de espera
description: Obtenga información sobre la actividad de espera
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Actividad de espera{#section_rlm_nft_dgb}

Si desea esperar antes de ejecutar la siguiente actividad en la ruta, puede utilizar una actividad **[!UICONTROL Wait]**. Permite definir el momento en que se ejecutará la siguiente actividad. Hay cuatro opciones disponibles:

* [Duración](#duration)
* [Fecha fija](#fixed_date)
* [Personalizado](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## Acerca de la actividad de espera{#about_wait}

Así es como se priorizan las esperas cuando se utilizan varias esperas en paralelo. Si tienen la misma configuración de tiempo y una condición diferente pero superpuesta, la espera colocada arriba será la que tenga prioridad. Por ejemplo, la condición de la primera espera es &quot;ser mujer&quot; y la condición de la segunda espera paralela es &quot;ser un VIP&quot;. Se asignará prioridad a la primera actividad de espera

También tenga en cuenta que si hay dos esperas diferentes en paralelo, se dará prioridad a la que se produzca primero, independientemente de su posición vertical. Por ejemplo, si se supera una espera de 1 hora y se supera una espera de 30 minutos, después de 30 minutos se procesará la espera de 30 minutos.

Puede definir una condición si desea restringir la espera a una determinada población.

>[!NOTE]
>
>La duración máxima de espera es de 30 días.
>
>En el modo de prueba, el parámetro **[!UICONTROL Wait time in test]** permite definir el tiempo que durará cada actividad de espera. El valor del tiempo predeterminado es de 10 segundos. Esto garantizará que los resultados de la prueba se obtengan rápidamente. Consulte [esta página](../building-journeys/testing-the-journey.md)

## Duración de espera{#duration}

Seleccione la duración de la espera antes de la ejecución de la siguiente actividad.

![](../assets/journey55.png)

## Se corrigió la fecha de espera{#fixed_date}

Seleccione la fecha de ejecución de la siguiente actividad.

![](../assets/journey56.png)

## Espera personalizada{#custom}

Esta opción le permite definir una fecha personalizada, por ejemplo, el 12 de julio de 2020 a las 17.00 horas, mediante una expresión avanzada basada en un campo procedente de un evento o de un origen de datos. No permite definir una duración personalizada, por ejemplo, 7 días. La expresión en el editor de expresiones debe proporcionar un formato dateTimeOnly. Consulte [esta página](../expression/expressionadvanced.md). Para obtener más información sobre el formato dateTimeOnly, consulte [esta página](../expression/data-types.md).

>[!NOTE]
>
>Puede aprovechar una expresión dateTimeOnly o utilizar una función para convertir a dateTimeOnly. Por ejemplo: ```toDateTimeOnly(@{Event.offerOpened.activity.endTime})```, siendo el campo del evento el formulario 2016-08-12T09:46:06Z.
>
>La **zona horaria** se espera en las propiedades del viaje. Como resultado, hoy no es posible desde la interfaz apuntar directamente a una marca de tiempo ISO-8601 completa, mezclando el tiempo y el huso horario como 2016-08-12T09:46:06.982-05. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
