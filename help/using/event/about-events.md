---
title: Acerca de los eventos
description: Obtenga información sobre cómo configurar un evento
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
source-wordcount: '715'
ht-degree: 76%

---


# Acerca de los eventos {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Acerca de los eventos"
>abstract="Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

Esta configuración es **obligatoria**[!DNL Journey Orchestration], ya que está diseñado para escuchar eventos y siempre la realiza un **usuario técnico**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. Puede utilizar varios eventos (en diferentes pasos de un recorrido) y varios recorridos pueden utilizar el mismo evento.

Si edita un evento utilizado en un recorrido en borrador o activo, solo puede cambiar el nombre, la descripción o agregar campos de carga útil. Limitamos estrictamente la edición de los recorridos en borrador o en directo para evitar que se rompan.

## Principio general {#section_r1f_xqt_pgb}

Los eventos son llamadas de API POST. Los eventos se envían a la plataforma de datos de Adobe Experience Cloud a través de las API de ingesta de flujos. El destino URL de los eventos enviados a través de las API de mensajería transaccional se denomina &quot;entrada&quot;. La carga útil de eventos sigue el formato XDM.

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). Existen dos modos para la transmisión de flujo continuo: autenticado y no autenticado. Para obtener más información sobre las API de ingesta de flujos, consulte [este vínculo](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/api/getting-started.html).

Después de llegar a través de las API de ingesta de flujos, los eventos fluyen a un servicio interno llamado Canalización y, a continuación, a la plataforma de datos. Si el esquema de evento tiene habilitado el indicador de Servicio de Perfil del cliente en tiempo real y un ID de conjunto de datos que también tiene el indicador de Perfil del cliente en tiempo real, se desplaza al servicio de Perfil del cliente en tiempo real.

The Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.

## Creación de un nuevo evento {#section_tbk_5qt_pgb}

Estos son los pasos principales para configurar un nuevo evento:

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Events]**. Se muestra la lista de eventos. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

   ![](../assets/journey5.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo evento. El panel de configuración de evento se abre en el lado derecho de la pantalla.

   ![](../assets/journey6.png)

1. Escriba un nombre para el evento.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción a su evento. Este paso es opcional.
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. Podrá utilizar esta información en su recorrido. Consulte [](../event/defining-the-payload-fields.md).
1. El número de recorridos que utiliza este evento se muestra en el campo **[!UICONTROL Used in]**. Puede hacer clic en el icono **[!UICONTROL View journeys]** para mostrar la lista de los recorridos con este evento.
1. Añada un área de nombres. Este paso es opcional, pero se recomienda, ya que la adición de un área de nombres le permite aprovechar la información almacenada en el servicio de Perfil del cliente en tiempo real. Define el tipo de clave que tiene el evento. Consulte [](../event/selecting-the-namespace.md).
1. Defina la clave: elija un campo de los campos de carga útil o defina una fórmula para identificar a la persona asociada al evento. Esta clave se configura automáticamente (pero aún puede editarse) si selecciona un Área de nombres. Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). Consulte [](../event/defining-the-event-key.md).
1. Añada una condición. Este paso es opcional. Esto permite al sistema procesar únicamente los eventos que cumplen la condición. La condición solo puede basarse en la información contenida en el evento. Consulte [](../event/adding-a-condition.md).
1. Haga clic **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   El evento está ahora configurado y listo para añadirse a un recorrido. Se requieren pasos de configuración adicionales para recibir eventos. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
