---
product: adobe campaign
solution: Journey Orchestration
title: Creación de un evento
description: Aprenda a crear un evento
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 53%

---


# Creación de un nuevo evento {#section_tbk_5qt_pgb}

Estos son los pasos principales para configurar un nuevo evento:

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Events]**. Se muestra la lista de eventos. Refer to [this page](../about/user-interface.md) for more information on the interface.

   ![](../assets/journey5.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo evento. El panel de configuración de evento se abre en el lado derecho de la pantalla. Escriba un nombre para el evento. También puede agregar una descripción.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. In the **[!UICONTROL Event ID type]** field, select the event type you want to use.

   ![](../assets/journey6bis.png)

   * **Eventos basados** en reglas: este tipo de evento no genera un eventID. En el campo de condición **de ID de** Evento, simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que activarán sus viajes. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de perfiles.

   * **Eventos generados** por el sistema: este tipo requiere un eventID. Este campo eventID se genera automáticamente al crear el evento y agregarse a la previsualización de carga útil. El sistema que empuja el evento no debe generar un ID, debe pasar el disponible en la previsualización de carga útil. Consulte [esta sección](../event/previewing-the-payload.md).
   >[!NOTE]
   >
   >Lea más sobre tipos de evento en [esta sección](../event/about-events.md).
1. El número de recorridos que utiliza este evento se muestra en el campo **[!UICONTROL Used in]**. Puede hacer clic en el icono **[!UICONTROL View journeys]** para mostrar la lista de los recorridos con este evento.
1. Defina los campos esquema y carga útil: aquí es donde selecciona la información de evento (generalmente denominada carga útil) que [!DNL Journey Orchestration] espera recibir. Podrá utilizar esta información en su recorrido. Consulte [esta página](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Cuando selecciona el **[!UICONTROL System Generated]** tipo, solo están disponibles los esquemas que tienen la mezcla de tipo eventID. Cuando selecciona el **[!UICONTROL Rule Based]** tipo, están disponibles todos los esquemas de Experience Evento.

1. Para eventos basados en reglas, haga clic dentro del **[!UICONTROL Event ID condition]** campo. Con el editor de expresiones simple, defina la condición que utilizará el sistema para identificar los eventos que activarán el viaje.
   ![](../assets/alpha-event6.png)

   En nuestro ejemplo, escribimos una condición basada en la ciudad del perfil. Esto significa que cada vez que el sistema recibe un evento que coincide con esta condición (**[!UICONTROL City]** campo y **[!UICONTROL Paris]** valor), lo pasa al Journey Orchestration.

1. Añada un área de nombres. Este paso es opcional, pero se recomienda, ya que la adición de un área de nombres le permite aprovechar la información almacenada en el servicio de Perfil del cliente en tiempo real. Define el tipo de clave que tiene el evento. Consulte [esta página](../event/selecting-the-namespace.md).
1. Defina la clave: elija un campo de los campos de carga útil o defina una fórmula para identificar a la persona asociada al evento. Esta clave se configura automáticamente (pero aún puede editarse) si selecciona un Área de nombres. De hecho, [!DNL Journey Orchestration] selecciona la clave que debe corresponder al área de nombres (por ejemplo, si selecciona un área de nombres de correo electrónico, se seleccionará la clave de correo electrónico). Consulte [esta página](../event/defining-the-event-key.md).
1. Para eventos generados por el sistema, puede agregar una condición. Este paso es opcional. Esto permite al sistema procesar únicamente los eventos que cumplen la condición. La condición solo puede basarse en la información contenida en el evento. Consulte [esta página](../event/adding-a-condition.md).
1. Haga clic **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   El evento está ahora configurado y listo para añadirse a un recorrido. Se requieren pasos de configuración adicionales para recibir eventos. Consulte [esta página](../event/additional-steps-to-send-events-to-journey-orchestration.md).