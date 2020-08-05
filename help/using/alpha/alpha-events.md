---
title: Eventos basados en reglas
description: Obtenga más información sobre los eventos basados en reglas.
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 9%

---


# Eventos basados en reglas{#simplified-events}

Hemos simplificado la forma de configurar eventos de experiencias. Estamos introduciendo un nuevo método que no requiere el uso de un eventID. Al configurar el evento en Journey Orchestration, ahora puede definir un evento basado en reglas.

Este nuevo tipo de evento no genera un eventID. Con el simple editor de expresiones, ahora simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que activarán sus viajes. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de perfiles.

Este nuevo método es mayormente transparente para los usuarios. El único cambio es un nuevo campo en la pantalla de definición de evento.

1. En el menú de la izquierda, haga clic en el **[!UICONTROL Admin]** icono y, a continuación, haga clic en **[!UICONTROL Events]**. Se muestra la lista de eventos.

   ![](../assets/alpha-event1.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo evento. El panel de configuración de evento se abre en el lado derecho de la pantalla.

   ![](../assets/alpha-event2.png)

1. Escriba el nombre del evento. También puede agregar una descripción.

   ![](../assets/alpha-event3.png)

1. In the new **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >El **[!UICONTROL System Generated]** tipo es el método existente que requiere un eventID. Consulte [esta sección](../event/about-events.md).

1. Defina la carga útil **[!UICONTROL Schema]** y **[!UICONTROL Fields]**. Consulte [esta sección](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Al seleccionar el **[!UICONTROL System Generated type]**, solo están disponibles los esquemas que tienen la mezcla de tipo eventID. Cuando selecciona el **[!UICONTROL Rule Based]** tipo, están disponibles todos los esquemas de Experience Evento.

1. Haga clic dentro del **[!UICONTROL Event ID condition]** campo. Con el editor de expresiones simple, defina la condición que utilizará el sistema para identificar los eventos que activarán el viaje.

   ![](../assets/alpha-event6.png)

   En nuestro ejemplo, escribimos una condición basada en la ciudad del perfil. Esto significa que cada vez que el sistema recibe un evento que coincide con esta condición (**[!UICONTROL City]** campo y **[!UICONTROL Paris]** valor), lo pasa al Journey Orchestration.

1. Defina el **[!UICONTROL Namespace]** y **[!UICONTROL Key]**. Consulte [Selección de la Área de nombres](../event/selecting-the-namespace.md) y [Definición de la clave](../event/defining-the-event-key.md)de evento.

   ![](../assets/alpha-event7.png)

Los demás pasos para la configuración del evento y la creación del viaje permanecen sin cambios.

El evento está ahora configurado y listo para ser lanzado en un viaje como cualquier otro evento. Cada vez que se envía al sistema un evento que coincide con la regla, se pasa al Journey Orchestration para activar los viajes.

