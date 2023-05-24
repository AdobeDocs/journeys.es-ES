---
product: adobe campaign
title: Fuente de datos de Adobe Experience Platform
description: Obtenga información sobre cómo configurar la fuente de datos de Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 14%

---

# Fuente de datos de Adobe Experience Platform {#concept_zrb_nqt_52b}

La fuente de datos de Adobe Experience Platform define la conexión al servicio Perfil del cliente en tiempo real. Esta fuente de datos está integrada y preconfigurada. No se puede eliminar. Esta fuente de datos está diseñada para recuperar y utilizar datos del servicio Perfil del cliente en tiempo real (por ejemplo, comprobar si la persona que ha introducido un recorrido es una mujer). Permite utilizar información del perfil y datos de los eventos de experiencia. Para obtener más información sobre el servicio Perfil del cliente en tiempo real, consulte esta sección [página](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es).

>[!NOTE]
>
>Puede recuperar los 1000 eventos de experiencia más recientes creados hace menos de un año.

Para permitir la conexión al servicio Perfil del cliente en tiempo real, debemos utilizar una clave para identificar a una persona y un área de nombres que contextualice la clave. Como resultado, solo puede utilizar este origen de datos si los recorridos comienzan con un evento que contiene una clave y un área de nombres. Consulte [esta página](../building-journeys/journey.md).

Puede editar el grupo de campos preconfigurado denominado &quot;ProfileFieldGroup&quot;, añadir otros nuevos y eliminar los que no se utilizan en ningún recorrido en borrador o activo. Consulte [esta página](../datasource/field-groups.md).

Estos son los pasos principales para agregar grupos de campos a la fuente de datos integrada.

1. En la lista de fuentes de datos, seleccione la fuente de datos integrada de Adobe Experience Platform.

   Se abre el panel de configuración de la fuente de datos en el lado derecho de la pantalla.

   ![](../assets/journey23.png)

1. Clic **[!UICONTROL Add a New Field Group]** para definir una nueva serie de campos que recuperar. Consulte [esta página](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Seleccione un esquema de la lista **[!UICONTROL Schema]** menú desplegable. Este campo enumera los esquemas de Perfil y Eventos de experiencia disponibles en Adobe Experience Platform. La creación de esquemas no se realiza en [!DNL Journey Orchestration]. Se realiza en Adobe Experience Platform.
1. Seleccione los campos que desee utilizar.
1. Haga clic en **[!UICONTROL Save]**.

Cuando coloque el cursor en el nombre de un grupo de campos, verá dos iconos a la derecha. Permiten eliminar y duplicar el grupo de campos. Tenga en cuenta que la variable **[!UICONTROL Delete]** solo está disponible si el grupo de campos no se utiliza en ningún recorrido activo o borrador (la información se muestra en la **[!UICONTROL Used in]** field).
