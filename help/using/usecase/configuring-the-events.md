---
title: Configuración de los eventos
description: Aprenda a configurar los eventos para el caso de uso avanzado del viaje
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---


# Configuración de los eventos {#concept_sbp_5cy_w2b}

En nuestro escenario, necesitamos recibir un evento cada vez que una persona entre al hotel Marlton y al restaurante. El usuario **** técnico necesita configurar los dos eventos que queremos que el sistema escuche en nuestro viaje.

Para obtener información adicional sobre la configuración de evento, consulte [](../event/about-events.md).

1. En el menú superior, haga clic en la **[!UICONTROL Events]** ficha y, a continuación, en **[!UICONTROL Add]** para crear un nuevo evento.

   ![](../assets/journeyuc1_1.png)

1. Introducimos el nombre sin espacios ni caracteres especiales: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. A continuación, seleccionamos el esquema y definimos la carga útil esperada para este evento. Seleccionamos los campos necesarios del modelo normalizado XDM. Necesitamos el ID de Experience Cloud para identificar a la persona en la base de datos de Perfil del cliente en tiempo real: &quot;endUserIDs > _experience > mcid > id&quot;.

   También necesitamos el token de registro para enviar mensajes push: &quot;_experience > campaña > mensaje > perfil > pushNotificationTokens > token&quot;

   Se genera automáticamente un ID para este evento. Este ID se almacena en el **[!UICONTROL eventID]** campo (&quot;_experience > campaña > orquestación > eventID&quot;). El sistema que empuja el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. En nuestro caso de uso, este ID se utiliza para identificar la ubicación de la señalización. Cada vez que una persona camina cerca de la señalización del vestíbulo, se envía un evento que contiene este ID de evento específico. El mismo principio se aplica a los eventos de señalización del restaurante. Esto permite al sistema saber qué señalización activó el envío del evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >La lista de los campos varía de un esquema a otro. Según la definición de esquema, algunos campos pueden ser obligatorios y estar preseleccionados.

1. Necesitamos seleccionar una Área de nombres. Una Área de nombres está preseleccionada en función de las propiedades de esquema. Puede mantener el preseleccionado. Para obtener más información sobre Áreas de nombres, consulte [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Se preselecciona una clave en función de las propiedades de esquema y la Área de nombres seleccionada. Puedes mantenerlo.

   ![](../assets/journeyuc2_4bis.png)

1. Haga clic **[!UICONTROL Save]**.

1. Haga clic en el **[!UICONTROL View Payload]** icono para previsualización de la carga útil esperada por el sistema y compartirla con la persona responsable del envío del evento.  Esta carga útil deberá configurarse en el postback de la consola de administración de Mobile Services.

   ![](../assets/journeyuc2_5.png)

Del mismo modo, crea el evento &quot;RestaurantBeacon&quot;. Sus dos eventos de señalización se crean y ahora se pueden utilizar en nuestro viaje. Ahora debe configurar la aplicación móvil para que pueda enviar la carga útil esperada al extremo de las API de inserción de flujo. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
