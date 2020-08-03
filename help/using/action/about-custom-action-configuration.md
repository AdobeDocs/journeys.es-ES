---
title: Acerca de la configuración de acciones personalizadas
description: Obtenga información sobre cómo configurar una acción personalizada
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 12%

---


# Acerca de la configuración de acciones personalizadas {#concept_sxy_bzs_dgb}

Si está utilizando un sistema de terceros para enviar mensajes o si desea [!DNL Journey Orchestration] enviar llamadas de API a un sistema de terceros, aquí es donde configura su conexión a [!DNL Journey Orchestration]. La acción personalizada definida por los usuarios técnicos estará disponible en la paleta izquierda del viaje, en la **[!UICONTROL Action]** categoría (consulte [](../building-journeys/about-action-activities.md). Estos son algunos ejemplos de sistemas a los que puede conectarse con acciones personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.
Las limitaciones se enumeran a continuación: [](../action/custom-action-limitations.md).

Estos son los pasos principales necesarios para configurar una acción personalizada:

1. En la **[!UICONTROL Actions]** lista, haga clic en **[!UICONTROL Add]** para crear una nueva acción. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/custom2.png)

1. Escriba un nombre para la acción.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción de la acción. Este paso es opcional.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. Consulte [](../action/url-configuration.md).
1. Configure la **[!UICONTROL Authentication]** sección. Esta configuración es la misma que para las fuentes de datos.  Consulte [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina el **[!UICONTROL Message parameters]**. Consulte [](../action/defining-the-message-parameters.md).
1. Haga clic **[!UICONTROL Save]**.

   La acción personalizada ahora está configurada y lista para utilizarse en sus viajes. Consulte [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Cuando se utiliza una acción personalizada en un viaje, la mayoría de los parámetros son de solo lectura. Sólo puede modificar los campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** y la **[!UICONTROL Authentication]** sección.
