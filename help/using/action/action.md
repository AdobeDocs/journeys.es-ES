---
product: adobe campaign
title: Acerca de las acciones
description: Obtenga información sobre cómo configurar una acción
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 72%

---

# Acerca de las acciones {#about_actions}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Acerca de las acciones"
>abstract="Aquí se define la conexión con el sistema que enviará los mensajes. Las acciones definidas aquí estarán disponibles en la paleta izquierda del recorrido, en la categoría Acción. "

Las acciones son conexiones a través de las cuales se ofrecen experiencias personalizadas en tiempo real a clientes, como notificaciones push, correo electrónico, SMS u otro medio de participación digital de su negocio.

Las acciones personalizadas permiten configurar la conexión de un sistema de terceros para enviar mensajes o llamadas API. Se puede configurar una acción con cualquier servicio de cualquier proveedor al que se pueda llamar mediante una API REST con carga útil en formato JSON.

Las acciones están disponibles en la paleta izquierda del recorrido, en la categoría **[!UICONTROL Action]**. Consulte [esta página](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>La configuración de las acciones personalizadas siempre la realiza un **usuario técnico**.

En la lista de **acciones**, puede pulsar c para crear un nuevo recorrido, acción, fuente de datos o evento. Para obtener más información sobre los métodos abreviados de teclado en [!DNL Journey Orchestration], vea [esta sección](../about/user-interface.md#section_ksq_zr1_ffb).

Para ver la lista de acciones o configurar una nueva acción, haga clic en **[!UICONTROL Actions]** en los menús superiores. Se muestra la lista de acciones. Consulte [esta página](../about/user-interface.md) para obtener más información sobre la interfaz.

![](../assets/custom1.png)

Si tiene Adobe Campaign Standard, debe configurar la acción predeterminada para enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard. Consulte [esta página](../action/working-with-adobe-campaign.md).

Si tiene Adobe Campaign v7 o v8, hay una integración disponible bajo petición. Consulte [esta página](../action/acc-action.md).

Si utiliza un sistema de terceros para enviar mensajes como Epsilon, Facebook, Adobe.io, Firebase, etc., debe agregar y configurar una acción personalizada. Consulte [esta página](../action/about-custom-action-configuration.md).

