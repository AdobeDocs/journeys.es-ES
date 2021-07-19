---
product: adobe campaign
title: Acerca de la configuración de acciones personalizadas
description: Obtenga información sobre cómo configurar una acción personalizada
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# Acerca de la configuración de acciones personalizadas {#concept_sxy_bzs_dgb}

Si utiliza un sistema de terceros para enviar mensajes o si desea que [!DNL Journey Orchestration] envíe llamadas de API a un sistema de terceros, aquí es donde configura su conexión a [!DNL Journey Orchestration]. La acción personalizada definida por los usuarios técnicos estará disponible en la paleta izquierda del recorrido, en la categoría **[!UICONTROL Action]** (consulte [esta página](../building-journeys/about-action-activities.md)). A continuación se muestran algunos ejemplos de sistemas a los que puede conectarse con acciones personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.
Las limitaciones se enumeran en [esta página](../about/limitations.md).

Estos son los pasos principales necesarios para configurar una acción personalizada:

1. En la lista **[!UICONTROL Actions]**, haga clic en **[!UICONTROL Add]** para crear una nueva acción. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/custom2.png)

1. Escriba un nombre para la acción.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción a la acción. Este paso es opcional.
1. El número de recorridos que utilizan esta acción se muestra en el campo **[!UICONTROL Used in]**. Puede hacer clic en el botón **[!UICONTROL View journeys]** para mostrar la lista de recorridos que utilizan esta acción.
1. Defina los diferentes parámetros **[!UICONTROL URL Configuration]**. Consulte [esta página](../action/url-configuration.md).
1. Configure la sección **[!UICONTROL Authentication]** . Esta configuración es la misma que para las fuentes de datos.  Consulte [esta sección](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina el **[!UICONTROL Message parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Haga clic en **[!UICONTROL Save]**.

   La acción personalizada ahora está configurada y lista para utilizarse en sus recorridos. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Cuando se utiliza una acción personalizada en un recorrido, la mayoría de los parámetros son de solo lectura. Solo puede modificar los campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** y la sección **[!UICONTROL Authentication]**.
