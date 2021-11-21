---
product: adobe campaign
title: Uso de un segmento
description: Aprenda a utilizar un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Uso de segmentos en condiciones {#using-a-segment}

En esta sección se explica cómo utilizar un segmento en una condición de recorrido. Para aprender a utilizar un **[!UICONTROL Segment qualification]** en su recorrido, consulte esta [sección](../building-journeys/segment-qualification-events.md).

Para utilizar un segmento en una condición de recorrido, siga estos pasos:

1. Abra un recorrido y suelte un **[!UICONTROL Condition]** actividad y elija la **Condición de fuente de datos**.
   ![](../assets/journey47.png)

1. Haga clic en **[!UICONTROL Add a path]** para cada ruta adicional necesaria. Para cada ruta, haga clic en el botón **[!UICONTROL Expression]** campo .

   ![](../assets/segment3.png)

1. En el lado izquierdo, despliegue **[!UICONTROL Segments]** nodo . Arrastre y suelte el segmento que desee utilizar para su condición. De forma predeterminada, la condición del segmento es verdadera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo las personas con la variable **Realizado** y **Existente** los estados de participación de segmentos se considerarán miembros del segmento. Para obtener más información sobre cómo evaluar un segmento, consulte la [Documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obtener más información sobre las condiciones de recorrido y cómo utilizar el editor de expresiones simple, consulte [Actividad de condición](../building-journeys/condition-activity.md#about_condition).
