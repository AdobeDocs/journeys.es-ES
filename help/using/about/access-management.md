---
title: Gestión de acceso
description: Más información sobre la administración del acceso
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Gestión de acceso{#concept_rfj_wpt_52b}

## Acerca de la administración de acceso {#about-access-management}

Los perfiles de producto se asignan a un conjunto de usuarios que comparten los mismos derechos dentro de la organización.

En la Consola de administración, puede asignar uno de los siguientes perfiles de producto predeterminados a los usuarios:

* **[!UICONTROL Limited Access User]**:: usuario con acceso de solo lectura a viajes e informes. Este perfil de producto incluye los siguientes derechos:
   * Leer viajes
   * Leer informes

* **[!UICONTROL Administrators]**:: usuario con acceso a los menús de administración con la posibilidad de administrar viajes, eventos e informes. Este perfil de producto incluye los siguientes derechos:
   * Administrar y ejecutar viajes
   * Administrar eventos, fuentes de datos y acciones
   * Administrar informes
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**es el único perfil de producto que permite crear, editar y publicar mensajes transaccionales (o plantillas de mensajería) en Adobe Campaign Standard. Este perfil de producto es necesario si utiliza Adobe Campaign Standard para enviar mensajes durante sus viajes.

* **[!UICONTROL Standard User]**:: usuario con acceso básico, como administración de viajes. Este perfil de producto incluye los siguientes derechos:
   * Administrar y ejecutar viajes
   * Administrar informes

Puede encontrar [aquí](../assets/do-not-localize/acs_rights_journeys.pdf) la compatibilidad entre los derechos y las diferentes funcionalidades de Journey Orquestation.

## Asignación de un perfil de producto {#assigning-product-profile}

Los perfiles de producto se administran en Admin Console. For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Para asignar un perfil de producto para que un usuario tenga acceso a la orquestación de viajes:

1. En la Consola de administración, seleccione **[!UICONTROL Journey orchestration]**.

   ![](../assets/user_management.png)

1. Seleccione el perfil de producto al que estará vinculado el nuevo usuario.

   ![](../assets/user_management_2.png)

1. Haga clic **[!UICONTROL Add user]**.

   También puede agregar el nuevo usuario a un grupo de usuarios para ajustar el conjunto compartido de permisos. Para obtener más información, consulte [esta página](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Escriba la dirección de correo electrónico del nuevo usuario y haga clic en **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

El usuario debe recibir un correo electrónico que le redirija a la instancia de orquestación de viajes.