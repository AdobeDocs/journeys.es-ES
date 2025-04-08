---
product: adobe campaign
title: Acerca de los segmentos de Adobe Experience Platform
description: Obtenga información sobre cómo configurar un segmento de Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 7%

---

# Acerca de los segmentos de Adobe Experience Platform {#about-segments}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


Si usas el [servicio de segmentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es) para crear tus segmentos, puedes aprovecharlos en [!DNL Journey Orchestration]. Gracias a una actividad de evento dedicada, puede hacer que las personas entren o avancen en un recorrido según las entradas y salidas de segmentos de Adobe Experience Platform. Esto también le permite crear condiciones complejas en los recorridos mediante el editor de expresiones simples o avanzadas.

Supongamos que tiene un segmento llamado &quot;cliente plata&quot;. Con esta actividad, puede hacer que todos los clientes nuevos de Silver Ingresen a un recorrido y les envíen una serie de mensajes personalizados. También puede generar fácilmente condiciones basadas en este segmento.

Estas son las posibilidades que [!DNL Journey Orchestration] le ofrece con los segmentos:

* Acceda a la lista de segmentos de Adobe Experience Platform. Consulte [Creación de un segmento](../segment/creating-a-segment.md).
* Cree segmentos directamente en [!DNL Journey Orchestration] de la misma manera que los crea usando el servicio de segmentación. Consulte [Creación de un segmento](../segment/creating-a-segment.md).
* Aproveche los segmentos en las condiciones de su recorrido mediante el editor de expresiones simples o avanzadas. Ver [Uso de segmentos en condiciones](../segment/using-a-segment.md).
* Agregue un evento **[!UICONTROL Segment qualification]** al recorrido para escuchar las entradas y salidas de perfiles en segmentos de Adobe Experience Platform. Ver [Actividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de evaluación en Journey Orchestration {#evaluation-method-in-journey-orchestration}

En Journey Orchestration, las audiencias se generan a partir de definiciones de segmentos mediante uno de estos métodos de evaluación:

* Segmentación de streaming: la lista de audiencias del segmento se mantiene actualizada en tiempo real mientras los nuevos datos fluyen al sistema.
* Segmentación por lotes: la lista de audiencias del segmento se actualiza cada hora en función de los datos recibidos durante la última hora.

El sistema determina la segmentación por lotes y la segmentación por flujo continuo para cada definición de segmento en función de la complejidad y el coste de evaluar la regla del segmento.

Puede ver el método de evaluación de cada segmento en la columna **[!UICONTROL Evaluation method]** de la lista de segmentos.

Después de definir un segmento por primera vez, los perfiles se añaden a la audiencia cuando cumplen los requisitos.

Rellenar el público a partir de datos anteriores puede tardar hasta 24 horas. Una vez que se ha rellenado el público, se mantiene actualizado continuamente y siempre está listo para la segmentación.