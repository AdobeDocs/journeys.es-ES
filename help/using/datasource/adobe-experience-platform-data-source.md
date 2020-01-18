---
title: 'Origen de datos de Adobe Experience Platform '
description: 'Obtenga información sobre cómo configurar la fuente de datos de Adobe Experience Platform '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Origen de datos de Adobe Experience Platform {#concept_zrb_nqt_52b}

El origen de datos de la plataforma de experiencia define la conexión al servicio de perfiles de cliente en tiempo real. Esta fuente de datos está integrada y preconfigurada. No se puede eliminar. Esta fuente de datos está diseñada para recuperar y utilizar datos del servicio de perfiles de cliente en tiempo real (por ejemplo, para comprobar si la persona que ha realizado un viaje es una mujer). Permite utilizar datos de perfil y datos de eventos de experiencia. Para obtener más información sobre el servicio de perfiles de cliente en tiempo real, consulte esta [página](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

>[!NOTE]
>
>Puede recuperar los 1000 eventos de experiencia más recientes creados hace menos de un año.

Para permitir la conexión al servicio de perfiles de cliente en tiempo real, debemos utilizar una clave para identificar a una persona y un espacio de nombres que contextualice la clave. Como resultado, solo puede utilizar este origen de datos si los viajes comienzan con un evento que contiene una clave y un espacio de nombres. Consulte [](../building-journeys/journey.md).

Puede editar el grupo de campos preconfigurado llamado &quot;ProfileFieldGroup&quot;, agregar otros nuevos y eliminar los que no se utilizan en ningún borrador o en ningún viaje en directo. Consulte [](../datasource/field-groups.md).

Estos son los pasos principales para agregar grupos de campos al origen de datos integrado.

1. En la lista de fuentes de datos, seleccione el origen de datos integrado de la plataforma de experiencias.

   Se abre el panel de configuración del origen de datos en el lado derecho de la pantalla.

   ![](../assets/journey23.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]**para definir una nueva serie de campos para recuperar. Consulte[](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Seleccione un esquema en la **[!UICONTROL Schema]**lista desplegable. Este campo enumera los esquemas de perfil y eventos de experiencia disponibles en la plataforma. La creación de esquemas no se realiza en la orquestación de trayectorias. Se realiza en la plataforma de datos.
1. Seleccione los campos que desee utilizar.
1. Defina la duración de la caché.
1. Haga clic en **[!UICONTROL Save]**.

Cuando coloque el cursor en el nombre de un grupo de campos, verá dos iconos a la derecha. Permiten eliminar y duplicar el grupo de campos. Tenga en cuenta que el **[!UICONTROL Delete]**icono solo está disponible si el grupo de campos no se utiliza en ningún viaje en directo o en borrador (la información se muestra en el**[!UICONTROL Used in]** campo).
