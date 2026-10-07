---
product: adobe campaign
title: Acerca de los segmentos de Adobe Experience Platform
description: Obtenga información sobre cómo configurar un segmento de Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 21%
---
# Acerca de los segmentos de Adobe Experience Platform {#about-segments}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


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