---
title: eventos de reacciones
description: Más información sobre los eventos de reacción
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
source-git-commit: 2b44cd9db7732c5e272b69e2583a5f81b4580d11
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# eventos de reacción {#section_dhx_gss_dgb}

Entre las distintas actividades de evento disponibles en la paleta, se encuentra el **[!UICONTROL Reactions]** evento integrado. Esta actividad le permite reaccionar a los datos de seguimiento relacionados con un mensaje enviado con actividades por correo electrónico, SMS o push en el mismo viaje. Esta información procede de los mensajes transaccionales en Adobe Campaign Standard. Capturamos esta información en tiempo real en el momento en que se comparte con el Adobe Experience Platform. En el caso de las notificaciones push, puede reaccionar a los mensajes en los que se ha hecho clic, se han enviado o se han producido errores. Para los mensajes SMS, puede reaccionar a los mensajes enviados o a los mensajes fallidos. En el caso de los mensajes de correo electrónico, puede reaccionar a los mensajes en los que se ha hecho clic, se ha enviado, se ha abierto o se han producido errores.

También puede utilizar este mecanismo para realizar una acción cuando no haya reacción a sus mensajes. Para ello, cree una segunda ruta paralela a la actividad de reacción y agregue una actividad de espera. Si no hay reacción durante el período definido en la actividad de espera, se elegirá la segunda ruta. Puede elegir enviar, por ejemplo, un mensaje de seguimiento.

Tenga en cuenta que solo puede usar una actividad de reacción en el lienzo si antes hay una actividad por correo electrónico, push o SMS.

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estos son los diferentes pasos para configurar los eventos de reacción:

1. Añada una **[!UICONTROL Label]** a la reacción. Este paso es opcional.
1. En la lista desplegable, seleccione la actividad de acción a la que desee reaccionar. Puede seleccionar cualquier actividad de acción situada en los pasos anteriores de la ruta.
1. En función de la acción seleccionada (un correo electrónico, un SMS o una notificación push), elija a qué desea responder.
1. Puede definir una condición como un paso opcional. Por ejemplo: después de una acción por correo electrónico, puede decidir crear dos rutas, una con un evento de reacción para rastrear clics solo para clientes VIP y otra con un evento de reacción para rastrear los clics realizados por mujeres.

>[!NOTE]
>
>Los eventos de reacciones funcionan con Adobe Campaign Standard, tanto si se implementan en servidores de AWS como de Azure.
>
>Los eventos de reacción no pueden rastrear las acciones de correo electrónico, SMS o push que tienen lugar en un viaje diferente.
>
>Los eventos de reacción rastrean los clics en los vínculos del tipo &quot;rastreados&quot; (consulte esta [página](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). No se tienen en cuenta los vínculos Bajas y de página espejo.

>[!IMPORTANT]
>
>Los clientes de correo electrónico como Gmail permiten el bloqueo de imágenes. Las aperturas de correo electrónico se rastrean con una imagen de 0 píxeles incluida en el correo electrónico. Si las imágenes están bloqueadas, las aperturas de correo electrónico no se tendrán en cuenta.
