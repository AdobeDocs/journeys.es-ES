---
title: Actividades de eventos
description: Más información sobre actividades de eventos
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
source-git-commit: 957e72de7feccb33684523e26b2bdccb2074e4ca
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 1%

---


# Actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (consulte [](../event/about-events.md) se muestran en la primera categoría de la paleta, en el lado izquierdo de la pantalla.

![](../assets/journey43.png)

Siempre inicio el viaje arrastrando y soltando una actividad de evento. También puede hacer clic con el doble.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede utilizar el **[!UICONTROL Label]** campo para agregar un sufijo al nombre del evento que aparecerá debajo de la actividad en el lienzo. Esto resulta útil para identificar sus eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilitará la depuración en caso de errores y facilitará la lectura de los informes.

![](../assets/journey33.png)

## eventos generales {#section_ofg_jss_dgb}

Para este tipo de evento, solo puede agregar una etiqueta y una descripción. No se puede editar el resto de la configuración. Fue realizado por el usuario técnico. Consulte [](../event/about-events.md).

## eventos de reacción {#section_dhx_gss_dgb}

Entre las distintas actividades de evento disponibles en la paleta, se encuentra el evento de **reacciones** integrado. Esta actividad le permite reaccionar a los datos de seguimiento relacionados con un mensaje enviado con actividades por correo electrónico, SMS o push en el mismo viaje. Esta información procede de los mensajes transaccionales en Adobe Campaign Standard. Capturamos esta información en tiempo real en el momento en que se comparte con la plataforma de datos. En el caso de las notificaciones push, puede reaccionar a los mensajes en los que se ha hecho clic, se han enviado o se han producido errores. Para los mensajes SMS, puede reaccionar a los mensajes enviados o a los mensajes fallidos. En el caso de los mensajes de correo electrónico, puede reaccionar a los mensajes en los que se ha hecho clic, se ha enviado, se ha abierto o se han producido errores.

También puede utilizar este mecanismo para realizar una acción cuando no haya reacción a sus mensajes. Para ello, cree una segunda ruta paralela a la actividad de reacción y agregue una actividad de espera. Si no hay reacción durante el período definido en la actividad de espera, se elegirá la segunda ruta. Puede elegir enviar, por ejemplo, un mensaje de seguimiento.

Tenga en cuenta que solo puede usar una actividad de reacción en el lienzo si antes hay una actividad por correo electrónico, push o SMS.

Consulte [](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estos son los diferentes pasos para configurar los eventos de reacción:

1. Añada una **[!UICONTROL Label]** a la reacción. Este paso es opcional.
1. En la lista desplegable, seleccione la actividad de acción a la que desee reaccionar. Puede seleccionar cualquier actividad de acción situada en los pasos anteriores de la ruta.
1. En función de la acción seleccionada (un correo electrónico, un SMS o una notificación push), elija a qué desea responder.
1. Puede definir una condición como un paso opcional. Por ejemplo: después de una acción por correo electrónico, puede decidir crear dos rutas, una con un evento de reacción para rastrear clics solo para clientes VIP y otra con un evento de reacción para rastrear los clics realizados por mujeres.

>[!NOTE]
>
>Los eventos de reacción no pueden rastrear las acciones de correo electrónico, SMS o push que tienen lugar en un viaje diferente.
>
>Los eventos de reacción rastrean los clics en los vínculos del tipo &quot;rastreados&quot; (consulte esta [página](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). No se tienen en cuenta los vínculos Bajas y de página espejo.

>[!CAUTION]
>
>Los clientes de correo electrónico como Gmail permiten el bloqueo de imágenes. Las aperturas de correo electrónico se rastrean con una imagen de 0 píxeles incluida en el correo electrónico. Si las imágenes están bloqueadas, las aperturas de correo electrónico no se tendrán en cuenta.

## eventos de calificación de segmentos {#segment-qualification}

Esta actividad permite que su viaje escuche las entradas y salidas de los perfiles en los segmentos de la Plataforma para hacer que los individuos entren o avancen en un viaje. For more information on segment creation, refer to this [section](../segment/about-segments.md).

Supongamos que tiene un segmento &quot;cliente plateado&quot;. Con esta actividad, puede hacer que todos los nuevos clientes plateados entren en un viaje y les envíen una serie de mensajes personalizados.

Este tipo de evento se puede posicionar como el primer paso o más tarde en el viaje.

Si el segmento se transmite con la opción Audiencias de alta frecuencia de Plataforma, las entradas y salidas se escuchan en tiempo real. Si el segmento no se transmite, las entradas y salidas se tienen en cuenta en el momento del cálculo del segmento.

1. Despliegue la categoría de **Eventos** y suelte una actividad **de calificación** de segmentos en el lienzo.

   ![](../assets/segment5.png)

1. Añada una **etiqueta** en la actividad. Este paso es opcional.

1. Haga clic en el campo **Segmento** y seleccione los segmentos que desee aprovechar.

   ![](../assets/segment6.png)

1. En el campo **Comportamiento** , elija si desea escuchar las entradas, salidas o ambos segmentos.

1. Seleccione una Área de nombres. Esto solo es necesario si el evento está posicionado como el primer paso del viaje.

   ![](../assets/segment7.png)

La carga útil contiene la siguiente información de contexto, que puede utilizar en condiciones y acciones:

* el comportamiento (entrada, salida)
* la marca de tiempo de la cualificación
* la identificación del segmento

## Uso avanzado: eventos con una espera en paralelo{#section_vxv_h25_pgb}

**¿Cómo se puede escuchar un evento sólo durante un tiempo determinado?**

Una actividad de evento situada en el viaje escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe agregar una actividad de espera paralela a la ruta de evento. El viaje escuchará el evento durante el tiempo especificado en la actividad de espera. Si se recibe un evento durante ese período, la persona fluirá por la ruta del evento. Si no es así, el cliente irá a la ruta de espera.

Por ejemplo, se ha enviado una primera notificación push de bienvenida a un cliente y se desea enviar una notificación push de descuento solo si el cliente entra en el restaurante en las siguientes 6 horas. Para ello, se crea un segundo camino (paralelo al evento uno) con una actividad de espera de 6 horas. Si el evento del restaurante se recibe menos de 6 horas después de la entrada de bienvenida, se envía la actividad push de descuento por comida. Si no se recibe ningún evento en las siguientes 6 horas, la persona pasa por el camino de espera.

![](../assets/journeyuc2_31.png)
