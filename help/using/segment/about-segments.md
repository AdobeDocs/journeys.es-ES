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
ht-degree: 2%

---

# Acerca de los segmentos de Adobe Experience Platform {#about-segments}

Si está utilizando el [Servicio de segmentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) para crear los segmentos, puede aprovecharlos en [!DNL Journey Orchestration]. Gracias a una actividad de evento dedicada, puede hacer que las personas entren o avancen en un recorrido según las entradas y salidas de segmentos de Adobe Experience Platform. Esto también le permite crear condiciones complejas en los recorridos mediante el editor de expresiones simples o avanzadas.

Supongamos que tiene un segmento llamado &quot;cliente plata&quot;. Con esta actividad, puede hacer que todos los clientes nuevos de Silver Ingresen a un recorrido y les envíen una serie de mensajes personalizados. También puede generar fácilmente condiciones basadas en este segmento.

Estas son las posibilidades [!DNL Journey Orchestration] le ofrecen con segmentos:

* Acceda a la lista de segmentos de Adobe Experience Platform. Consulte [Creación de segmentos](../segment/creating-a-segment.md).
* Creación de segmentos directamente en [!DNL Journey Orchestration] del mismo modo que se crean mediante el servicio de segmentación. Consulte [Creación de segmentos](../segment/creating-a-segment.md).
* Aproveche los segmentos en las condiciones de su recorrido mediante el editor de expresiones simples o avanzadas. Consulte [Uso de segmentos en condiciones](../segment/using-a-segment.md).
* Añadir un **[!UICONTROL Segment qualification]** a su recorrido para escuchar las entradas y salidas de perfiles en segmentos de Adobe Experience Platform. Consulte [Actividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de evaluación en el Journey Orchestration {#evaluation-method-in-journey-orchestration}

En Journey Orchestration, las audiencias se generan a partir de definiciones de segmento utilizando uno de estos métodos de evaluación:

* Segmentación de streaming: la lista de audiencias del segmento se mantiene actualizada en tiempo real mientras los nuevos datos fluyen al sistema.
* Segmentación por lotes: la lista de audiencias del segmento se actualiza cada hora en función de los datos recibidos durante la última hora.

El sistema determina la segmentación por lotes y la segmentación por flujo continuo para cada definición de segmento en función de la complejidad y el coste de evaluar la regla del segmento.

Puede ver el método de evaluación para cada segmento en la **[!UICONTROL Evaluation method]** de la lista de segmentos.

Después de definir un segmento por primera vez, los perfiles se añaden a la audiencia cuando cumplen los requisitos.

Realizar una copia de seguridad de la audiencia a partir de datos anteriores puede tardar hasta 24 horas. Una vez que la audiencia se ha rellenado, se mantiene actualizada continuamente y siempre está lista para la segmentación.