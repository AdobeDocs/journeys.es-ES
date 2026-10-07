---
product: adobe campaign
title: Creación de segmentos
description: Aprenda a utilizar un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: f84dc133-3b70-479e-b5be-a155d892fec0
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
source-wordcount: '192'
ht-degree: 42%
---
# Creación de segmentos {#creating-a-segment}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


Puede crear un segmento utilizando el [Servicio de segmentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es) o puede acceder a ellos y crearlos directamente en [!DNL Journey Orchestration].

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Segments]**. Se muestra la lista de segmentos de Adobe Experience Platform. Puede buscar un segmento específico en la lista.

   ![](../assets/segment1.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo segmento. La pantalla de definición del segmento le permite configurar todos los campos obligatorios para definir el segmento. La configuración es la misma que en el servicio de segmentación. Consulte la [guía de usuario del Generador de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=es).

   ![](../assets/segment2.png)

El segmento ahora se puede usar en los recorridos para generar condiciones o agregar un evento **[!UICONTROL Segment qualification]**. Ver [Uso de segmentos en condiciones](../segment/using-a-segment.md) y [Actividades de eventos](../building-journeys/segment-qualification-events.md).
