---
product: adobe campaign
title: Configuración de los eventos
description: Obtenga información sobre cómo configurar los eventos para el caso de uso avanzado de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 7%

---

# Configuración de los eventos {#concept_sbp_5cy_w2b}

En nuestro escenario, necesitamos recibir un evento cada vez que una persona entre al hotel Marlton y al restaurante. El **usuario técnico** necesita configurar los dos eventos que queremos que el sistema escuche en nuestro recorrido.

Para obtener más información sobre la configuración de eventos, consulte [esta página](../event/about-events.md).

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Events]** y haga clic en **[!UICONTROL Add]** para crear un nuevo evento.

   ![](../assets/journeyuc1_1.png)

1. Introducimos el nombre sin espacios ni caracteres especiales: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. A continuación, seleccionamos el esquema y definimos la carga útil esperada para este evento. Seleccionamos los campos necesarios del modelo normalizado XDM. Necesitamos el ID de Experience Cloud para identificar a la persona en la base de datos del perfil del cliente en tiempo real: &quot;endUserIDs > _experience > mcid > id&quot;.

   También necesitamos el token de registro para enviar mensajes push: &quot;_experience > campaña > mensaje > perfil > pushNotificationTokens > token&quot;

   Se genera automáticamente un ID para este evento. Este ID se almacena en el campo **[!UICONTROL eventID]** (&quot;_experience > campaign > orchestration > eventID&quot;). El sistema que impulsa el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. En nuestro caso de uso, este ID se utiliza para identificar la ubicación de la señalización. Cada vez que una persona camina cerca de la señalización de vestíbulo, se envía un evento que contiene este ID de evento específico. El mismo principio se aplica a los eventos de señalización del restaurante. Esto permite al sistema saber qué señalización activó la entrega del evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >La lista de campos varía de un esquema a otro. Según la definición del esquema, algunos campos pueden ser obligatorios y estar preseleccionados.

1. Necesitamos seleccionar un área de nombres. Un área de nombres está preseleccionada en función de las propiedades de esquema. Puede mantener la preseleccionada. Para obtener más información sobre áreas de nombres, consulte [esta página](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Se preselecciona una clave en función de las propiedades de esquema y el espacio de nombres seleccionado. Puedes mantenerlo.

   ![](../assets/journeyuc2_4bis.png)

1. Haga clic en **[!UICONTROL Save]**.

1. Haga clic en el icono **[!UICONTROL View Payload]** para previsualizar la carga útil que espera el sistema y compártala con la persona responsable del envío del evento.  Esta carga útil debe configurarse en el postback de la consola de administración de Mobile Services.

   ![](../assets/journeyuc2_5.png)

Del mismo modo, cree el evento &quot;RestaurantBeacon&quot;. Los dos eventos de señalización se crean y ahora se pueden utilizar en nuestro recorrido. Ahora necesita configurar la aplicación móvil para que pueda enviar la carga útil esperada al extremo de las API de ingesta de transmisión. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).
