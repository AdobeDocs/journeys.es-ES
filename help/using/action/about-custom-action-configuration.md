---
product: adobe campaign
title: Acerca de la configuración de acciones personalizadas
description: Obtenga información sobre cómo configurar una acción personalizada
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# Acerca de la configuración de acciones personalizadas {#concept_sxy_bzs_dgb}

Si utiliza un sistema de terceros para enviar mensajes o si lo desea [!DNL Journey Orchestration] para enviar llamadas de API a un sistema de terceros, aquí es donde configura su conexión a [!DNL Journey Orchestration]. La acción personalizada definida por los usuarios técnicos estará disponible en la paleta izquierda del recorrido, en **[!UICONTROL Action]** categoría (consulte [esta página](../building-journeys/about-action-activities.md). Estos son algunos ejemplos de sistemas a los que puede conectarse con acciones personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.

Las limitaciones se enumeran en [esta página](../about/limitations.md).

En los parámetros de acción personalizados, puede pasar una colección simple, así como una colección de objetos. Con respecto a las limitaciones, consulte [esta página](../usecase/collections.md#limitations). Tenga en cuenta también que los parámetros tienen un formato esperado (por ejemplo: cadena, decimal, etc.). Debe tener cuidado de respetar estos formatos esperados. Consulte esta sección [caso de uso](../usecase/collections.md).

Estos son los pasos principales necesarios para configurar una acción personalizada:

1. Desde el **[!UICONTROL Actions]** , haga clic en **[!UICONTROL Add]** para crear una acción nueva. El panel de configuración de acción se abre en el lado derecho de la pantalla.

   ![](../assets/custom2.png)

1. Escriba un nombre para la acción.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción a la acción. Este paso es opcional.
1. El número de recorridos que utilizan esta acción se muestra en la variable **[!UICONTROL Used in]** field. Puede hacer clic en **[!UICONTROL View journeys]** para mostrar la lista de recorridos con esta acción.
1. Defina los diferentes **[!UICONTROL URL Configuration]** parámetros. Consulte [esta página](../action/url-configuration.md).
1. Configure las variables **[!UICONTROL Authentication]** sección. Esta configuración es la misma que para las fuentes de datos.  Consulte [esta sección](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina el **[!UICONTROL Action parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Haga clic en **[!UICONTROL Save]**.

   La acción personalizada ahora está configurada y lista para utilizarse en sus recorridos. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Cuando se utiliza una acción personalizada en un recorrido, la mayoría de los parámetros son de solo lectura. Solo puede modificar la variable **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** y el **[!UICONTROL Authentication]** sección.
