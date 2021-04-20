---
product: adobe campaign
solution: Journey Orchestration
title: Uso de un segmento
description: Aprenda a utilizar un segmento
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# Uso de segmentos en condiciones {#using-a-segment}

En esta sección se explica cómo utilizar un segmento en una condición de recorrido. Para aprender a utilizar un evento **[!UICONTROL Segment qualification]** en su recorrido, consulte esta [sección](../building-journeys/segment-qualification-events.md).

Para utilizar un segmento en una condición de recorrido, siga estos pasos:

1. Abra un recorrido, suelte una actividad **[!UICONTROL Condition]** y elija la **Condición de fuente de datos**.
   ![](../assets/journey47.png)

1. Haga clic **[!UICONTROL Add a path]** para cada ruta adicional necesaria. Para cada ruta, haga clic en el campo **[!UICONTROL Expression]** .

   ![](../assets/segment3.png)

1. En el lado izquierdo, despliegue el nodo **[!UICONTROL Segments]**. Arrastre y suelte el segmento que desee utilizar para su condición. De forma predeterminada, la condición del segmento es verdadera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo las personas con los estados de participación de segmentos **Realized** y **Existing** se considerarán miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [Documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obtener más información sobre las condiciones de recorrido y cómo utilizar el editor de expresiones simple, consulte [Actividad de condición](../building-journeys/condition-activity.md#about_condition).