---
title: eventos basados en reglas
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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 6%

---


# eventos basados en reglas{#simplified-events}

Hemos simplificado la forma de configurar eventos de experiencias. Estamos introduciendo un nuevo método que no requiere el uso de un eventID. Al configurar el evento en Journey Orchestration, ahora puede definir un evento basado en reglas.

Este nuevo tipo de evento no genera un eventID. Con el simple editor de expresiones, ahora simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que activarán sus viajes. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de perfiles.

Este nuevo método es mayormente transparente para los usuarios. El único cambio es un nuevo campo en la pantalla de definición de evento.

1. En el menú de la izquierda, haga clic en el icono **Administración** y, a continuación, haga clic en **Eventos**. Se muestra la lista de eventos.

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. El panel de configuración de evento se abre en el lado derecho de la pantalla.

   ![](../assets/alpha-event2.png)

1. Escriba el nombre del evento. También puede agregar una descripción.

   ![](../assets/alpha-event3.png)

1. En el nuevo campo de tipo **de ID de** Evento, seleccione Basado en **reglas**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >El tipo Generado **por** el sistema es el método existente que requiere un eventID. Consulte [esta sección](../event/about-events.md).

1. Defina el **Esquema** y los **campos** de carga útil. Consulte [esta sección](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Cuando se selecciona el tipo **Generado por** el sistema, solo están disponibles los esquemas que tienen la mezcla de tipo eventID. Cuando selecciona el tipo **Basado** en reglas, están disponibles todos los esquemas de Experience Evento.

1. Haga clic dentro del campo Condición **de ID de** Evento. Con el editor de expresiones simple, defina la condición que utilizará el sistema para identificar los eventos que activarán el viaje.

   ![](../assets/alpha-event6.png)

   En nuestro ejemplo, escribimos una condición basada en la ciudad del perfil. Esto significa que cada vez que el sistema recibe un evento que coincide con esta condición (campo **Ciudad** y valor de **París** ), lo pasa al Journey Orchestration.

1. Defina la **Área de nombres** y la **clave**. Consulte [Selección de la Área de nombres](../event/selecting-the-namespace.md) y [Definición de la clave](../event/defining-the-event-key.md)de evento.

   ![](../assets/alpha-event7.png)

Los demás pasos para la configuración del evento y la creación del viaje permanecen sin cambios.

El evento está ahora configurado y listo para ser lanzado en un viaje como cualquier otro evento. Cada vez que se envía al sistema un evento que coincide con la regla, se pasa al Journey Orchestration para activar los viajes.

