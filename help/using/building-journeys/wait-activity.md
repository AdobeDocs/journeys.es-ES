---
product: adobe campaign
title: Actividad de espera
description: Descubra más información sobre la actividad de espera
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 10%

---

# Actividad de espera{#section_rlm_nft_dgb}

Si desea esperar antes de ejecutar la siguiente actividad en la ruta, puede utilizar un **[!UICONTROL Wait]** actividad. Permite definir el momento en el que se ejecutará la siguiente actividad. Hay tres opciones disponibles:

* [Duración](#duration)
* [Personalizado](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## Acerca de la actividad Espera{#about_wait}

Así se priorizan las esperas cuando se utilizan varias esperas en paralelo. Si tienen la misma configuración de tiempo y una condición diferente, pero superpuesta, la espera colocada arriba será la priorizada. VIP Por ejemplo, la condición de la primera espera es &quot;ser mujer&quot; y la condición de la segunda espera en paralelo es &quot;ser una mujer&quot; (ser un hombre) o &quot;ser una mujer&quot; (ser un hombre), o &quot;ser una mujer&quot; (ser una mujer). Se dará prioridad a la primera actividad de espera.

Tenga en cuenta también que si dos esperas diferentes están en paralelo, la que se produce primero tendrá prioridad, independientemente de su posición vertical. Por ejemplo, si se supera una espera de 1 hora y se reduce una espera de 30 minutos, después de 30 minutos, se procesa la espera de 30 minutos.

>[!NOTE]
>
>La duración máxima de la espera es de 30 días.
>
>En el modo de prueba, la variable **[!UICONTROL Wait time in test]** permite definir el tiempo que durará cada actividad de espera. El tiempo predeterminado es 10 segundos. Esto garantizará que obtenga los resultados de la prueba rápidamente. Consulte [esta página](../building-journeys/testing-the-journey.md)

## Duración de espera{#duration}

Seleccione la duración de la espera antes de la ejecución de la siguiente actividad.

![](../assets/journey55.png)

## Espera personalizada{#custom}

Esta opción le permite definir una fecha personalizada, por ejemplo, el 12 de julio de 2020 a las 17:00, mediante una expresión avanzada basada en un campo proveniente de un evento o una fuente de datos. No permite definir una duración personalizada, por ejemplo, de 7 días. La expresión en el editor de expresiones debe proporcionar un formato dateTimeOnly. Consulte [esta página](../expression/expressionadvanced.md). Para obtener más información sobre el formato dateTimeOnly, consulte [esta página](../expression/data-types.md).

>[!NOTE]
>
>Puede aprovechar una expresión dateTimeOnly o utilizar una función para convertirla en dateTimeOnly. Por ejemplo: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), siendo el campo del evento del formulario 2016-08-12T09:46:06Z.
>
>El **zona horaria** se espera en las propiedades del recorrido. Como resultado, hoy en día no es posible desde la interfaz apuntar directamente a una marca de tiempo ISO-8601 completa mezclando la hora y el desplazamiento de zona horaria como 2016-08-12T09:46:06.982-05. Consulte [esta página](../building-journeys/timezone-management.md).

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
