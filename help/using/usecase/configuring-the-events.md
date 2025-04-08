---
product: adobe campaign
title: Configuración de los eventos
description: Obtenga información sobre cómo configurar los eventos para el caso de uso avanzado de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 7%

---

# Configuración de los eventos {#concept_sbp_5cy_w2b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


En nuestro caso, tenemos que recibir un evento cada vez que una persona entre en el hotel Marlton y en el restaurante. El **usuario técnico** debe configurar los dos eventos que queremos que el sistema escuche en nuestro recorrido.

Para obtener información adicional sobre la configuración de eventos, consulte [esta página](../event/about-events.md).

1. En el menú superior, haga clic en la ficha **[!UICONTROL Events]** y haga clic en **[!UICONTROL Add]** para crear un nuevo evento.

   ![](../assets/journeyuc1_1.png)

1. Introducimos el nombre sin espacios ni caracteres especiales: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Luego seleccionamos el esquema y definimos la carga útil esperada para este evento. Se seleccionan los campos necesarios del modelo normalizado de XDM. Necesitamos el Experience Cloud ID para identificar a la persona en la base de datos del perfil del cliente en tiempo real: &quot;endUserIDs > _experience > mcid > id&quot;.

   También se necesita el token de registro para enviar mensajes push: &quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   Se genera automáticamente un ID para este evento. Este ID se almacena en el campo **[!UICONTROL eventID]** (&quot;_experience > campaign > orchestration > eventID&quot;). El sistema que impulsa el evento no debe generar un ID, debe utilizar el que está disponible en la previsualización de carga útil. En nuestro caso de uso, este ID se utiliza para identificar la ubicación de la señalización. Cada vez que una persona camine cerca de la señalización de vestíbulo, se enviará un evento que contendrá este ID de evento específico. El mismo principio se aplica a los eventos de señalización de restaurante. Esto permite al sistema saber qué señalización activó el envío de eventos.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >La lista de campos varía según el esquema. Según la definición del esquema, algunos campos pueden ser obligatorios y preseleccionados.

1. Necesitamos seleccionar un área de nombres. Un área de nombres está preseleccionada en función de las propiedades de esquema. Puede mantener la preseleccionada. Para obtener más información sobre áreas de nombres, vea [esta página](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Una clave se preselecciona en función de las propiedades de esquema y el área de nombres seleccionada. Te lo puedes quedar.

   ![](../assets/journeyuc2_4bis.png)

1. Haga clic en **[!UICONTROL Save]**.

1. Haga clic en el icono **[!UICONTROL View Payload]** para previsualizar la carga útil que espera el sistema y compartirla con la persona responsable del envío del evento.  Esta carga útil debe configurarse en el postback de la consola de administración de Mobile Services.

   ![](../assets/journeyuc2_5.png)

Del mismo modo, cree el evento RestaurantBeacon. Se crean sus dos eventos de señalización y ahora se pueden utilizar en nuestro recorrido. Ahora debe configurar la aplicación móvil para que pueda enviar la carga útil esperada al extremo de las API de ingesta de transmisión. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).
