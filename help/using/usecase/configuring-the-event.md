---
product: adobe campaign
solution: Journey Orchestration
title: Configuración del evento
description: Obtenga información sobre cómo configurar el evento para el caso de uso simple de recorrido
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 8%

---


# Configuración del evento{#concept_y44_hcy_w2b}

En nuestro escenario, necesitamos recibir un evento cada vez que una persona camina cerca de una señalización colocada junto al spa. El **usuario técnico** necesita configurar el evento que el sistema escuchará en nuestro recorrido.

Para obtener más información sobre la configuración de eventos, consulte [esta página](../event/about-events.md).

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Events]** y haga clic en **[!UICONTROL Add]** para crear un nuevo evento.

   ![](../assets/journeyuc1_1.png)

1. Introducimos el nombre sin espacios ni caracteres especiales: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. A continuación, seleccionamos el esquema y definimos la carga útil esperada para este evento. Seleccionamos los campos necesarios del modelo normalizado XDM. Necesitamos el ID de Experience Cloud para identificar a la persona en la base de datos del perfil del cliente en tiempo real: _endUserIDs > experience > mcid > id_. Se genera automáticamente un ID para este evento. Este ID se almacena en el campo **[!UICONTROL eventID]** (_experience > campaign > orchestration > eventID_). El sistema que impulsa el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. En nuestro caso de uso, este ID se utiliza para identificar la ubicación de la señalización. Cada vez que una persona camina cerca de la señalización de spa, se envía un evento que contiene este ID de evento específico. Esto permite al sistema saber qué señalización activó la entrega del evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >La lista de campos varía de un esquema a otro. Según la definición del esquema, algunos campos pueden ser obligatorios y estar preseleccionados.

1. Necesitamos seleccionar un área de nombres. Un área de nombres está preseleccionada en función de las propiedades de esquema. Puede mantener la preseleccionada. Para obtener más información sobre áreas de nombres, consulte [esta página](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Se preselecciona una clave en función de las propiedades de esquema y el espacio de nombres seleccionado. Puedes mantenerlo.

   ![](../assets/journeyuc1_5.png)

1. Haga clic en **[!UICONTROL Save]**.

1. Haga clic en el icono **[!UICONTROL View Payload]** para previsualizar la carga útil que espera el sistema y compártala con la persona responsable del envío del evento. Esta carga útil debe configurarse en el postback de la consola de administración de Mobile Services.

   ![](../assets/journeyuc1_7.png)

   El evento está listo para utilizarse en el recorrido. Ahora necesita configurar la aplicación móvil para que pueda enviar la carga útil esperada al extremo de las API de ingesta de transmisión. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).