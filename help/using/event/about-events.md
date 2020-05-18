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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 1%

---


# Acerca de los eventos {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Acerca de los eventos"
>abstract="Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). Esto es lo que la Orquestación de Viaje escuchará en los viajes para orquestar las mejores próximas acciones."

Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). Esto es lo que la Orquestación de Viaje escuchará en los viajes para orquestar las mejores próximas acciones.

Esta configuración es **obligatoria**, ya que la orquestación de viajes está diseñada para escuchar eventos y siempre la realiza un usuario **** técnico.

La configuración de evento permite definir la información que la orquestación de viajes recibirá como eventos. Puede utilizar varios eventos (en diferentes pasos de un viaje) y varios viajes pueden utilizar el mismo evento.

Si edita un evento utilizado en un viaje en borrador o activo, solo puede cambiar el nombre, la descripción o agregar campos de carga útil. Limitamos estrictamente la edición de los viajes en borrador o en directo para evitar que se rompan los viajes.

## Principio general {#section_r1f_xqt_pgb}

Los Eventos son llamadas de API POST. Los Eventos se envían a la plataforma de datos de Adobe Experience Cloud a través de las API de inserción de flujo. El destino URL de los eventos enviados a través de las API de mensajería transaccional se denomina &quot;entrada&quot;. La carga útil de eventos sigue el formato XDM.

La carga útil contiene la información requerida por las API de inserción de flujo para funcionar (en el encabezado) y la información requerida por la orquestación de viajes para funcionar (el ID de evento, parte del cuerpo de carga útil) y la información que se va a utilizar en los viajes (en el cuerpo, por ejemplo, la cantidad de un carro abandonado). Existen dos modos para la transmisión de flujo continuo, autenticado y no autenticado. Para obtener más información sobre las API de inserción de flujo, consulte [este vínculo](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html).

Después de llegar a través de las API de inserción de flujo, los eventos fluyen a un servicio interno llamado Canalización y, a continuación, a la plataforma de datos. Si el esquema de evento tiene habilitado el indicador de Servicio de Perfil del cliente en tiempo real y un ID de conjunto de datos que también tiene el indicador de Perfil del cliente en tiempo real, se desplaza al servicio de Perfil del cliente en tiempo real.

Los eventos de filtros de tubería que tienen una carga útil que contiene ID de eventos de orquestación de trayectos (consulte el proceso de creación de eventos que se muestra a continuación) proporcionados por Orquestación de trayectos y contenidos en la carga útil de evento. Estos eventos son escuchados por la Orquestación de Viaje y se activa el viaje correspondiente.

## Creating a new event {#section_tbk_5qt_pgb}

Estos son los pasos principales para configurar un nuevo evento:

1. En el menú superior, haga clic en la **[!UICONTROL Events]** ficha. Se muestra la lista de eventos. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

   ![](../assets/journey5.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo evento. El panel de configuración de evento se abre en el lado derecho de la pantalla.

   ![](../assets/journey6.png)

1. Escriba un nombre para el evento.

   >[!NOTE]
   >
   >No utilice espacios ni caracteres especiales. No utilice más de 30 caracteres.

1. Añada una descripción a su evento. Este paso es opcional.
1. Defina los campos esquema y carga útil: aquí es donde selecciona la información de evento (generalmente denominada carga útil) que la orquestación de viajes espera recibir. Podrá utilizar esta información en su viaje. Consulte [](../event/defining-the-payload-fields.md).
1. El número de viajes que utilizan este evento se muestra en el **[!UICONTROL Used in]** campo. Puede hacer clic en el **[!UICONTROL View journeys]** icono para mostrar la lista de los viajes con este evento.
1. Añada una Área de nombres. Este paso es opcional, pero se recomienda ya que la adición de una Área de nombres le permite aprovechar la información almacenada en el servicio de Perfil al cliente en tiempo real. Define el tipo de clave que tiene el evento. Consulte [](../event/selecting-the-namespace.md).
1. Defina la clave: elija un campo de los campos de carga útil o defina una fórmula para identificar a la persona asociada al evento. Esta clave se configura automáticamente (pero aún puede editarse) si selecciona una Área de nombres. De hecho, la orquestación de viajes selecciona la clave que debe corresponder a la Área de nombres (por ejemplo, si selecciona una Área de nombres de correo electrónico, se seleccionará la clave de correo electrónico). Consulte [](../event/defining-the-event-key.md).
1. Añada una condición. Este paso es opcional. Esto permite al sistema procesar únicamente los eventos que cumplen la condición. La condición solo puede basarse en la información contenida en el evento. Consulte [](../event/adding-a-condition.md).
1. Haga clic **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   El evento está ahora configurado y listo para ser entregado en un viaje. Se requieren pasos de configuración adicionales para recibir eventos. Consulte [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
