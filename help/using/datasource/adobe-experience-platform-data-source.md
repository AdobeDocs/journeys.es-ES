---
product: adobe campaign
title: 'Fuente de datos de Adobe Experience Platform '
description: 'Obtenga información sobre cómo configurar la fuente de datos de Adobe Experience Platform '
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 11%

---

# Fuente de datos de Adobe Experience Platform {#concept_zrb_nqt_52b}

La fuente de datos de Adobe Experience Platform define la conexión con el servicio Perfil del cliente en tiempo real. Esta fuente de datos está integrada y preconfigurada. No se puede eliminar. Esta fuente de datos está diseñada para recuperar y utilizar datos del servicio Perfil del cliente en tiempo real (por ejemplo, comprobar si la persona que ha introducido un recorrido es una mujer). Permite utilizar datos de perfil y datos de eventos de experiencia. Para obtener más información sobre el Servicio de Perfil del Cliente en tiempo real, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es).

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
