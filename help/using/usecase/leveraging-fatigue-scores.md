---
title: Puntuaciones de fatiga de aprovechamiento
description: Aprenda a aprovechar las puntuaciones de fatiga en los viajes
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Puntuaciones de fatiga de aprovechamiento {#concept_dsh_1ry_wfb}

Este caso de uso le mostrará cómo aprovechar los puntajes de fatiga para evitar que los clientes se interesen demasiado en sus viajes.

>[!CAUTION]
>
>La capacidad de puntuación de fatiga predictiva solo está disponible para los clientes que utilicen la función del servicio de datos estándar de Adobe Campaign.

## Configuración del evento {#section_ptb_ws1_ffb}

Siga los pasos descritos en [](../event/about-events.md).

## Configuración del origen de datos {#section_o3n_4yy_wfb}

Realice los siguientes pasos para seleccionar los campos de puntuación de fatiga en el origen de datos integrado:

1. En el menú superior, haga clic en la **[!UICONTROL Data Sources]**ficha y seleccione el origen de datos integrado de la plataforma de experiencias.

   ![](../assets/journey23.png)

1. Compruebe que los campos requeridos para el caso de uso están seleccionados.
1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione el**[!UICONTROL Profiles]** modelo y agregue los campos **[!UICONTROL fatigueLevel]**y**[!UICONTROL fatigueScore]** (en _travesíaAI > emailScore > fatiga_).

   ![](../assets/journeyuc3_1.png)

1. Haga clic **[!UICONTROL Save]**.

## Construyendo el viaje {#section_uzm_pyy_wfb}

Para crear, validar y publicar el viaje, siga los pasos descritos en [](../building-journeys/journey.md).

En nuestro caso de uso, estamos aprovechando el **[!UICONTROL fatigueLevel]**campo. También puede utilizar el**[!UICONTROL fatigueScore]** campo.

Realice los siguientes pasos para aprovechar el nivel de fatiga del viaje:

1. Agregue un evento y una condición en el viaje.

   ![](../assets/journeyuc2_14.png)

1. Elija el **[!UICONTROL Data Source Condition]**tipo y haga clic en el**[!UICONTROL Expression]** campo.

   ![](../assets/journeyuc3_2.png)

1. Con el editor de expresiones simples, busque el **[!UICONTROL fatigueLevel]**campo (_ExperiencePlatformDataSource > JourneyAIScores > Profile > travelAI > emailScore > fatigue_), suéltelo a la derecha y cree la siguiente condición: &quot;fatigueLevel es igual a &quot;Low&quot;. Haga clic**[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   La expresión avanzada es:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. En la condición, cree otras dos rutas para niveles de fatiga medios y altos.

   ![](../assets/journeyuc3_4.png)

1. Ahora puede agregar diferentes acciones para cada nivel de fatiga.

   ![](../assets/journeyuc3_5.png)
