---
product: adobe campaign
title: Acerca de los segmentos de Adobe Experience Platform
description: Obtenga información sobre cómo configurar un segmento de Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# Acerca de los segmentos de Adobe Experience Platform {#about-segments}

Si utiliza el [Servicio de segmentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) para crear sus segmentos, puede aprovecharlos en [!DNL Journey Orchestration]. Gracias a una actividad de evento dedicada, puede hacer que las personas entren o avancen en un recorrido en función de las entradas y salidas de segmentos de Adobe Experience Platform. Esto también le permite crear condiciones complejas en sus recorridos con el editor de expresiones simple o avanzado.

Supongamos que tiene un segmento &quot;cliente plata&quot;. Con esta actividad, puede hacer que todos los clientes nuevos de plata introduzcan un recorrido y envíen una serie de mensajes personalizados. También puede crear fácilmente condiciones basadas en este segmento.

Estas son las posibilidades que [!DNL Journey Orchestration] le ofrece con los segmentos:

* Acceda a la lista de segmentos de Adobe Experience Platform. Consulte [Creación de un segmento](../segment/creating-a-segment.md).
* Cree segmentos directamente en [!DNL Journey Orchestration] de la misma manera que los crea mediante el servicio de segmentación. Consulte [Creación de un segmento](../segment/creating-a-segment.md).
* Aproveche los segmentos en las condiciones de su recorrido con el editor de expresiones simple o avanzada. Consulte [Uso de segmentos en condiciones](../segment/using-a-segment.md).
* Añada un evento **[!UICONTROL Segment qualification]** al recorrido para escuchar las entradas y salidas de perfiles en segmentos de Adobe Experience Platform. Consulte [Actividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de evaluación en el Journey Orchestration {#evaluation-method-in-journey-orchestration}

En Journey Orchestration, las audiencias se generan a partir de definiciones de segmentos utilizando uno de estos métodos de evaluación:

* Segmentación por transmisión : la lista de audiencia del segmento se mantiene actualizada en tiempo real mientras los nuevos datos fluyen al sistema.
* Segmentación por lotes: la lista de audiencia del segmento se actualiza cada hora, según los datos que hayan llegado en la hora anterior.

El sistema determina la segmentación por lotes y la segmentación de flujo continuo para cada definición de segmento, en función de la complejidad y el coste de la evaluación de la regla de segmento.

Puede ver el método de evaluación para cada segmento en la columna **[!UICONTROL Evaluation method]** de la lista de segmentos.

Después de haber definido un segmento por primera vez, los perfiles se añaden a la audiencia cuando cumplen los requisitos.

Rellenar la audiencia a partir de datos anteriores puede tardar hasta 24 horas. Una vez que la audiencia se ha rellenado, se mantiene actualizada de forma continua y siempre está lista para la segmentación.