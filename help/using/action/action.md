---
title: Acerca de las acciones
description: Obtenga información sobre cómo configurar una acción
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
source-git-commit: 87910a9f3dbf2c34776a8d2ab1f00426e8b0704c
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 3%

---


# Acerca de las acciones {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Acerca de las acciones"
>abstract="Aquí es donde se define la conexión con el sistema que enviará los mensajes. Las acciones definidas aquí estarán disponibles en la paleta izquierda del viaje, en la categoría Acción. "

Las acciones son conexiones a través de las cuales se ofrecen experiencias personalizadas en tiempo real a clientes como notificaciones push, correo electrónico, SMS o cualquier otro medio de participación digital que se utilice en su negocio.

Las acciones personalizadas le permiten configurar la conexión de un sistema de terceros para enviar mensajes o llamadas de API. Se puede configurar una acción con cualquier servicio de cualquier proveedor al que se pueda llamar mediante una API REST con una carga útil con formato JSON.

Las acciones están disponibles en la paleta izquierda del viaje, en la **[!UICONTROL Action]** categoría (véase [](../building-journeys/about-action-activities.md) ).

>[!NOTE]
>
>La configuración de las acciones personalizadas siempre la realiza un usuario **** técnico.

En la lista de **acciones**, puede pulsar c para crear un nuevo viaje, acción, fuente de datos o evento. Para obtener más información sobre los métodos abreviados de teclado en Orquestación de viajes, consulte [](../about/user-interface.md#section_ksq_zr1_ffb).

Para vista de la lista de acción o configurar una nueva acción, haga clic en **[!UICONTROL Actions]** en los menús superiores. Se muestra la lista de acciones. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

![](../assets/custom1.png)

Si tiene Adobe Campaign Standard, debe configurar la acción predeterminada para enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard. Consulte [](../action/working-with-adobe-campaign.md).

Si utiliza un sistema de terceros para enviar mensajes como Epsilon, Facebook, Adobe.io, Firebase, etc., debe agregar y configurar una acción personalizada. Consulte [](../action/about-custom-action-configuration.md).

Para obtener más información sobre cómo configurar una acción para orquestación de viajes y cómo utilizarla en un viaje, vea este [vídeo tutorial](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html).
