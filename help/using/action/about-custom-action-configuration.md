---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de la configuración de acciones personalizadas
description: Obtenga información sobre cómo configurar una acción personalizada
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# Acerca de la configuración de acciones personalizadas {#concept_sxy_bzs_dgb}

Si está utilizando un sistema de terceros para enviar mensajes o si desea [!DNL Journey Orchestration] enviar llamadas de API a un sistema de terceros, aquí es donde configura su conexión a [!DNL Journey Orchestration]. La acción personalizada definida por los usuarios técnicos estará disponible en la paleta izquierda del viaje, en la categoría **[!UICONTROL Action]** (consulte [esta página](../building-journeys/about-action-activities.md). Estos son algunos ejemplos de sistemas a los que puede conectarse con acciones personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.
Las limitaciones se enumeran en [esta página](../about/limitations.md).

Estos son los pasos principales necesarios para configurar una acción personalizada:

1. En la lista **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]** para crear una nueva acción. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/custom2.png)

1. Escriba un nombre para la acción.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción de la acción. Este paso es opcional.
1. El número de viajes que utilizan esta acción se muestra en el campo **[!UICONTROL Used in]**. Puede hacer clic en el botón **[!UICONTROL View journeys]** para mostrar la lista de los viajes mediante esta acción.
1. Defina los diferentes parámetros **[!UICONTROL URL Configuration]**. Consulte [esta página](../action/url-configuration.md).
1. Configure la sección **[!UICONTROL Authentication]**. Esta configuración es la misma que para las fuentes de datos.  Consulte [esta sección](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina el **[!UICONTROL Message parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Haga clic en **[!UICONTROL Save]**.

   La acción personalizada ahora está configurada y lista para utilizarse en sus viajes. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Cuando se utiliza una acción personalizada en un viaje, la mayoría de los parámetros son de solo lectura. Sólo puede modificar los campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** y la sección **[!UICONTROL Authentication]**.
