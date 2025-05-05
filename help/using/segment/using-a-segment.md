---
product: adobe campaign
title: Uso de segmentos en condiciones
description: Aprenda a utilizar un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 4%

---

# Uso de segmentos en condiciones {#using-a-segment}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


En esta sección se explica cómo utilizar un segmento en una condición de recorrido. Para aprender a utilizar un evento **[!UICONTROL Segment qualification]** en el recorrido, consulte esta [sección](../building-journeys/segment-qualification-events.md).

Para utilizar un segmento en una condición de recorrido, siga estos pasos:

1. Abra un recorrido, suelte una actividad **[!UICONTROL Condition]** y elija la **condición de Source de datos**.
   ![](../assets/journey47.png)

1. Haga clic en **[!UICONTROL Add a path]** para cada ruta adicional necesaria. Para cada ruta, haga clic en el campo **[!UICONTROL Expression]**.

   ![](../assets/segment3.png)

1. En el lado izquierdo, despliegue el nodo **[!UICONTROL Segments]**. Arrastre y suelte el segmento que desee utilizar para la condición. De forma predeterminada, la condición del segmento es verdadera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo las personas con los estados de participación en los segmentos **Realized** y **Existing** se considerarán como miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=es#interpret-segment-results).

Para obtener más información sobre las condiciones de recorrido y cómo usar el editor de expresiones simple, consulte [Actividad de la condición](../building-journeys/condition-activity.md#about_condition).
