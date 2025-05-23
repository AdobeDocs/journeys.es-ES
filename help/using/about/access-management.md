---
product: adobe campaign
title: Administración de acceso
description: Más información sobre la administración de acceso.
feature: Journeys
role: User
level: Intermediate
exl-id: a551efa5-c0d8-4138-96ca-fb407fad8c59
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 83%

---

# Administración de acceso{#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._



## Acerca de la administración de acceso {#about-access-management}

[!DNL Journey Orchestration] Le permite asignar un conjunto de permisos a los usuarios para definir a qué parte de la interfaz pueden acceder.

Pueden ser administrados por administradores que tengan acceso a Admin Console. Para obtener más información sobre Admin Console, consulte la [Guía de administración de empresas y equipos](https://helpx.adobe.com/es/enterprise/managing/user-guide.html).

Para poder acceder a [!DNL Journey Orchestration], un usuario debe cumplir lo siguiente:

* ser parte de un **[!UICONTROL product profile]** de [!DNL Journey Orchestration] asociado a permisos de [!DNL Journey Orchestration].
* Ser parte de un **[!UICONTROL product profile]** de [!DNL Adobe Experience Platform]. No hay ningún permiso obligatorio que tener. El usuario debe tener el permiso **[!UICONTROL profile management]** para poder crear y editar segmentos de plataforma desde la interfaz de [!DNL Journey Orchestration]. Para obtener más información, consulte [esta página](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=es#adobe-admin-console).

En Admin Console, puede asignar a los usuarios uno de los siguientes perfiles de producto predeterminados:

* **[!UICONTROL Limited Access User]**: usuario con acceso de solo lectura a recorridos e informes. Este perfil de productos incluye los siguientes permisos:
   * Leer recorridos
   * Leer informes

* **[!UICONTROL Administrators]**: usuario con acceso a los menús de administración con la posibilidad de administrar recorridos, eventos e informes. Este perfil de productos incluye los siguientes permisos:
   * Administrar recorridos
   * Publicar recorridos
   * Administrar eventos, fuentes de datos y acciones
   * Administrar informes

  >[!NOTE]
  >
  >**[!UICONTROL Administrators]** es el único perfil de productos que permite crear, editar y publicar mensajes transaccionales (o plantillas de mensajería) en Adobe Campaign Standard. Este perfil de producto es necesario si utiliza Adobe Campaign Standard para enviar mensajes en los recorridos. No se debe cambiar el nombre en Admin Console.

* **[!UICONTROL Standard User]**: usuario con acceso básico, como administración de recorridos. Este perfil de productos incluye los siguientes permisos:
   * Administrar recorridos
   * Publicar recorridos
   * Administrar informes
   * Lea eventos, fuentes de datos y acciones

También puede crear sus propios perfiles de producto si los perfiles predeterminados no son suficientes para administrar a los usuarios.
Los usuarios siempre deben estar vinculados a un perfil de producto que le permita asignarles permisos de integración específicos como:

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

A continuación se muestra la compatibilidad entre los permisos y las diferentes funcionalidades de [!DNL Journey Orchestration].

![](../assets/do-not-localize/journey_permission.png)

## Creación de un perfil de producto {#create-product-profile}

[!DNL Journey Orchestration] le permite crear sus propios perfiles de productos, y asignar un conjunto de permisos y zonas protegidas a los usuarios. Con los perfiles del producto, puede autorizar o denegar el acceso a determinadas funcionalidades u objetos de la interfaz.

Para obtener más información sobre cómo crear y administrar zonas protegidas, consulte la documentación de [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=es).

Para crear un perfil de producto, y asignar un conjunto de permisos y zonas protegidas, haga lo siguiente:

1. En Admin Console, seleccione **[!UICONTROL Journey Orchestration]**. En la pestaña **[!UICONTROL Product profile]**, haga clic en **[!UICONTROL New Profile]**.

   ![](../assets/do-not-localize/user_management_5.png)

1. Añada un **[!UICONTROL Profile Name]** y **[!UICONTROL Description]** para el nuevo perfil de productos. Si desea que el perfil **[!UICONTROL Display name]** sea diferente, desmarque **[!UICONTROL Same as Profile Name]** y escriba su **[!UICONTROL Display name]**.

1. En la categoría **[!UICONTROL User Notifications]**, elija si se notificará por correo electrónico a los usuarios cuando se agreguen o eliminen de este perfil de productos.

1. Cuando termine, haga clic en **[!UICONTROL Done]**. Se ha creado el nuevo perfil de productos.

   ![](../assets/do-not-localize/user_management_1.png)

1. Seleccione el nuevo perfil de productos para empezar a administrar permisos. En la pestaña **[!UICONTROL Users]**, agregue usuarios al perfil del producto. Para obtener más información, consulte [esta página](../about/access-management.md#assigning-product-profile).

1. Lleve a cabo los mismos pasos que se detallan arriba para agregar **[!UICONTROL Admin]** a su perfil de productos.

1. En la pestaña **[!UICONTROL Permissions]**, seleccione una de las dos categorías **[!UICONTROL Sandbox]** o **[!UICONTROL Authoring]** para abrir la página **[!UICONTROL Edit Permissions]**, y agregar o quitar permisos para el perfil del producto.

   ![](../assets/do-not-localize/user_management_7.png)

1. En la categoría de permisos **[!UICONTROL Sandboxes]**, elija qué zonas protegidas desea asignar al perfil del producto. En **[!UICONTROL Available Permissions Items]**, haga clic en el icono de signo más (+) para asignar zonas protegidas al perfil. Para obtener más información sobre las zonas protegidas, consulte esta [sección](../about/access-management.md#sandboxes).

   ![](../assets/do-not-localize/user_management_8.png)

1. Si es necesario, en **[!UICONTROL Included Permission Items]** haga clic en el icono X para eliminar los permisos del perfil del producto.

   ![](../assets/do-not-localize/user_management_9.png)

1. Desde la categoría de permisos **[!UICONTROL Authoring]**, realice los mismos pasos que se describen arriba para agregar permisos al perfil del producto.
   <br>Para obtener más información sobre los permisos y la compatibilidad entre los permisos y las diferentes funcionalidades de [!DNL Journey Orchestration], consulte esta [sección](../about/access-management.md#about-access-management).

   ![](../assets/do-not-localize/user_management_10.png)

1. Cuando termine, haga clic en **[!UICONTROL Save]**.

El perfil del producto se ha creado y configurado. Los usuarios vinculados a este perfil ahora pueden conectarse a [!DNL Journey Orchestration].

## Asignación de un perfil de producto {#assigning-product-profile}

Los perfiles de producto se asignan a un conjunto de usuarios que comparten los mismos permisos dentro de la organización.
La lista de todos los perfiles de productos listos para usar con permisos asignados se encuentra en esta sección.

Para asignar un perfil de producto para que un usuario tenga acceso [!DNL Journey Orchestration]:

1. En Admin Console, seleccione **[!UICONTROL Journey Orchestration]**.

   ![](../assets/do-not-localize/user_management.png)

1. Seleccione el perfil de producto al que estará vinculado su nuevo usuario.

   ![](../assets/do-not-localize/user_management_2.png)

1. Haga clic en **[!UICONTROL Add user]**.

   También puede agregar el nuevo usuario a un grupo de usuarios para ajustar el conjunto compartido de permisos. Para obtener más información, consulte [esta página](https://helpx.adobe.com/es/enterprise/using/user-groups.html).

   ![](../assets/do-not-localize/user_management_3.png)

1. Escriba la dirección de correo electrónico del nuevo usuario y haga clic en **[!UICONTROL Save]**.

   ![](../assets/do-not-localize/user_management_4.png)

El usuario debe recibir un correo electrónico que le redirija a su instancia [!DNL Journey Orchestration].

## Uso de zonas protegidas {#sandboxes}

[!DNL Journey Orchestration] le permite particionar la instancia en entornos virtuales separados, llamados zonas protegidas.
Las zonas protegidas se asignan mediante perfiles de producto en Admin Console. Para obtener más información sobre cómo asignar zonas protegidas, consulte esta [sección](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] refleja las zonas protegidas de Adobe Experience Platform creadas para una organización determinada.
Las zonas protegidas de Adobe Experience Platform se pueden crear o restablecer desde la instancia de Adobe Experience Platform. Consulte la [guía del usuario de zonas protegidas](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=es) para conocer los pasos detallados.

Encontrará el control del conmutador de zonas protegidas en la parte superior izquierda de la pantalla. Para cambiar de una zona protegida a otra, haga clic en la zona protegida activa y seleccione otra zona protegida en la lista desplegable.
