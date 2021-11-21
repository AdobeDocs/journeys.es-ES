---
product: adobe campaign
title: Uso de las puntuaciones de fatiga
description: Aprenda a aprovechar las puntuaciones de fatiga en recorridos
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# Aprovechamiento de la IA en el recorrido {#concept_dsh_1ry_wfb}

Este caso de uso le muestra cómo aprovechar las puntuaciones de fatiga para evitar saturar a sus clientes de sus recorridos.

>[!NOTE]
>
>La capacidad de puntuación de fatiga predictiva solo está disponible para los clientes que usan la variable [Data Connectors de Adobe Experience Platform](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Configuración del evento {#section_ptb_ws1_ffb}

Siga los pasos descritos en [esta página](../event/about-events.md).

## Configuración de la fuente de datos {#section_o3n_4yy_wfb}

Siga estos pasos para seleccionar los campos de puntuación de fatiga en la fuente de datos integrada:

1. En el panel de menú, seleccione **[!UICONTROL Admin]**. En el **[!UICONTROL Data sources]** , haga clic en **[!UICONTROL Manage]**.
1. Seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Compruebe que los campos requeridos para su caso de uso estén seleccionados.
1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione **[!UICONTROL Profiles]** y añada el **[!UICONTROL fatigueLevel]** y **[!UICONTROL fatigueScore]** campos (en _journeyAI > emailScore > fatiga_).

   ![](../assets/journeyuc3_1.png)

1. Haga clic en **[!UICONTROL Save]**.

## Construcción del recorrido {#section_uzm_pyy_wfb}

Para crear, validar y publicar el recorrido, siga los pasos descritos en [esta página](../building-journeys/journey.md).

En nuestro caso de uso, estamos aprovechando el **[!UICONTROL fatigueLevel]** campo . También puede usar la variable **[!UICONTROL fatigueScore]** campo .

Siga estos pasos para aprovechar el nivel de fatiga del recorrido:

1. Añada un evento y una condición en el recorrido.

   ![](../assets/journeyuc2_14.png)

1. Elija el tipo **[!UICONTROL Data Source Condition]** y haga clic en el campo **[!UICONTROL Expression]** . 

   ![](../assets/journeyuc3_2.png)

1. Con el editor de expresiones simple, busque la variable **[!UICONTROL fatigueLevel]** campo (_ExperiencePlatformDataSource > JourneyAIScores > Perfil > journeyAI > emailScore > fatiga_), suéltela a la derecha y cree la siguiente condición: &quot;fatigueLevel es igual a &quot;Low&quot;. Haga clic en **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   La expresión avanzada es:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. En la condición , cree otras dos rutas para niveles de fatiga medios y altos.

   ![](../assets/journeyuc3_4.png)

1. Ahora puede agregar diferentes acciones para cada nivel de fatiga.

   ![](../assets/journeyuc3_5.png)
