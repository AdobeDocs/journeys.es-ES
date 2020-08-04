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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---


# Acerca de las acciones {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Acerca de las acciones"
>abstract="Aquí se define la conexión con el sistema que enviará los mensajes. Las acciones definidas aquí estarán disponibles en la paleta izquierda del recorrido, en la categoría Acción. "

Las acciones son conexiones a través de las cuales se ofrecen experiencias personalizadas en tiempo real a clientes, como notificaciones push, correo electrónico, SMS u otro medio de participación digital de su negocio.

Las acciones personalizadas le permiten configurar la conexión de un sistema de terceros para enviar mensajes o llamadas API. Se puede configurar una acción con cualquier servicio de cualquier proveedor al que se pueda llamar mediante una API REST con carga útil en formato JSON.

Las acciones están disponibles en la paleta izquierda del recorrido, en la categoría **[!UICONTROL Action]** (véase [](../building-journeys/about-action-activities.md) ).

>[!NOTE]
>
>La configuración de las acciones personalizadas siempre la realiza un **usuario técnico**.

En la lista de **acciones**, puede pulsar c para crear un nuevo recorrido, acción, fuente de datos o evento. Para obtener más información sobre los métodos abreviados de teclado en [!DNL Journey Orchestration], consulte [](../about/user-interface.md#section_ksq_zr1_ffb).

Para ver la lista de acciones o configurar una nueva acción, haga clic en **[!UICONTROL Actions]** en los menús superiores. Se muestra la lista de acciones. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

![](../assets/custom1.png)

Si tiene Adobe Campaign Standard, debe configurar la acción predeterminada para enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard. Consulte [](../action/working-with-adobe-campaign.md).

Si utiliza un sistema de terceros para enviar mensajes como Epsilon, Facebook, Adobe.io, Firebase, etc., debe agregar y configurar una acción personalizada. Consulte [](../action/about-custom-action-configuration.md).

Para obtener más información sobre cómo configurar una acción para [!DNL Journey Orchestration] y cómo utilizarla en un recorrido, vea este [vídeo tutorial](https://docs.adobe.com/content/help/es-ES/journey-orchestration-learn/tutorials/configure-actions.html).
