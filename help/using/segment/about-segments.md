---
title: Acerca de los segmentos de Adobe Experience Platform
description: Obtenga información sobre cómo configurar un segmento de Adobe Experience Platform
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# Acerca de los segmentos de Adobe Experience Platform {#about-segments}

Si utiliza el servicio [de segmentación de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) Adobe Experience Platform para crear sus segmentos, puede aprovecharlos en [!DNL Journey Orchestration]. Gracias a una actividad de evento dedicada, puede hacer que los individuos entren o avancen en un viaje basado en entradas y salidas de segmentos de Adobe Experience Platform. Esto también le permite crear condiciones complejas en sus viajes con el editor de expresiones simple o avanzado.

Supongamos que tiene un segmento &quot;cliente plateado&quot;. Con esta actividad, puede hacer que todos los nuevos clientes plateados entren en un viaje y les envíen una serie de mensajes personalizados. También puede crear fácilmente condiciones basadas en este segmento.

Estas son las posibilidades [!DNL Journey Orchestration] de oferta con los segmentos:

* Acceda a la lista de segmentos de Adobe Experience Platform. See [Creating a segment](../segment/creating-a-segment.md).
* Cree segmentos directamente del [!DNL Journey Orchestration] mismo modo que los crea con el servicio de segmentación. See [Creating a segment](../segment/creating-a-segment.md).
* Aproveche los segmentos en las condiciones del viaje con el editor de expresiones simple o avanzado. Consulte [Uso de segmentos en condiciones](../segment/using-a-segment.md).
* Añada un **[!UICONTROL Segment qualification]** evento a su viaje para escuchar las entradas y salidas de perfiles en segmentos de Adobe Experience Platform. Consulte actividades [de](../building-journeys/segment-qualification-events.md)Eventos.
