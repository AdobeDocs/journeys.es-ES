---
product: adobe campaign
solution: Journey Orchestration
title: 'Fuentes de datos de Adobe Experience Platform '
description: 'Obtenga información sobre cómo configurar la fuente de datos de Adobe Experience Platform '
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 11%

---


# Fuentes de datos de Adobe Experience Platform {#concept_zrb_nqt_52b}

La fuente de datos de Adobe Experience Platform define la conexión con el servicio Perfil del cliente en tiempo real. Esta fuente de datos está integrada y preconfigurada. No se puede eliminar. Esta fuente de datos está diseñada para recuperar y utilizar datos del servicio Perfil del cliente en tiempo real (por ejemplo, comprobar si la persona que ha introducido un recorrido es una mujer). Permite utilizar datos de perfil y datos de eventos de experiencia. Para obtener más información sobre el Servicio de Perfil del Cliente en tiempo real, consulte esta [página](https://docs.adobe.com/content/help/es-ES/experience-platform/profile/home.html).

>[!NOTE]
>
>Puede recuperar los 1000 últimos eventos de experiencia creados hace menos de un año.

Para permitir la conexión con el servicio de Perfil del cliente en tiempo real, debemos utilizar una clave para identificar a una persona y un área de nombres que contextualice la clave. Como resultado, solo puede utilizar esta fuente de datos si sus recorridos empiezan por un evento que contenga una clave y un área de nombres. Consulte [esta página](../building-journeys/journey.md).

Puede editar el grupo de campos preconfigurado llamado &quot;ProfileFieldGroup&quot;, agregar nuevos y eliminar los que no se usan en borradores o recorridos activos. Consulte [esta página](../datasource/field-groups.md).

Estos son los pasos principales para agregar grupos de campos al origen de datos integrado.

1. En la lista de fuentes de datos, seleccione la fuente de datos integrada de Adobe Experience Platform.

   Se abre el panel de configuración de la fuente de datos en el lado derecho de la pantalla.

   ![](../assets/journey23.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]** para definir una nueva serie de campos que desea recuperar. Consulte [esta página](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Seleccione un esquema en la lista desplegable **[!UICONTROL Schema]**. Este campo enumera los esquemas de perfil y eventos de experiencia disponibles en Adobe Experience Platform. La creación del esquema no se realiza en [!DNL Journey Orchestration]. Se realiza en Adobe Experience Platform.
1. Seleccione los campos que desee utilizar.
1. Defina la duración de la caché.
1. Haga clic en **[!UICONTROL Save]**.

Cuando coloque el cursor en el nombre de un grupo de campos, verá dos iconos a la derecha. Permiten eliminar y duplicar el grupo de campos. Tenga en cuenta que el icono **[!UICONTROL Delete]** solo está disponible si el grupo de campos no se utiliza en ningún recorrido activo o borrador (información que se muestra en el campo **[!UICONTROL Used in]** ).
