---
product: adobe campaign
title: Uso de segmentos en condiciones
description: Aprenda a utilizar un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# Uso de segmentos en condiciones {#using-a-segment}

En esta sección se explica cómo utilizar un segmento en una condición de recorrido. Para aprender a utilizar un **[!UICONTROL Segment qualification]** en el recorrido, consulte esta sección [sección](../building-journeys/segment-qualification-events.md).

Para utilizar un segmento en una condición de recorrido, siga estos pasos:

1. Abra un recorrido y suelte un **[!UICONTROL Condition]** y elija la **Condición de fuente de datos**.
   ![](../assets/journey47.png)

1. Clic **[!UICONTROL Add a path]** para cada ruta adicional necesaria. Para cada ruta, haga clic en **[!UICONTROL Expression]** field.

   ![](../assets/segment3.png)

1. En el lado izquierdo, despliegue **[!UICONTROL Segments]** nodo. Arrastre y suelte el segmento que desee utilizar para la condición. De forma predeterminada, la condición del segmento es verdadera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo las personas con el **Realizado** y **Existente** los estados de participación en el segmento se considerarán miembros del mismo. Para obtener más información sobre cómo evaluar un segmento, consulte la [Documentación del Servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obtener más información sobre las condiciones de recorrido y cómo utilizar el editor de expresiones simple, consulte [Actividad de condición](../building-journeys/condition-activity.md#about_condition).
