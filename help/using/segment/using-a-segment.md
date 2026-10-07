---
product: adobe campaign
title: Uso de segmentos en condiciones
description: Aprenda a utilizar un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
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
source-wordcount: '221'
ht-degree: 27%
---
# Uso de segmentos en condiciones {#using-a-segment}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


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
   >Solo las personas con los estados de participación en los segmentos **Realized** y **Existing** se considerarán como miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obtener más información sobre las condiciones de recorrido y cómo usar el editor de expresiones simple, consulte [Actividad de la condición](../building-journeys/condition-activity.md#about_condition).
