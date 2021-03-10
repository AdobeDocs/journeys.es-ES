---
product: adobe campaign
solution: Journey Orchestration
title: Eventos de reacción
description: Más información sobre los eventos de reacción
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 1%

---


# Eventos de reacción {#section_dhx_gss_dgb}

Entre las distintas actividades de evento disponibles en la paleta, se encuentra el evento **[!UICONTROL Reactions]** integrado. Esta actividad le permite reaccionar ante el seguimiento de datos relacionados con un mensaje enviado con actividades de correo electrónico, SMS o push dentro del mismo recorrido. Esta información se obtiene a partir de la mensajería transaccional en Adobe Campaign Standard. Capturamos esta información en tiempo real en el momento en que se comparte con Adobe Experience Platform. Para las notificaciones push, puede reaccionar a mensajes en los que se ha hecho clic, enviados o en los que se han producido errores. En el caso de los mensajes SMS, puede reaccionar ante los mensajes enviados o fallidos. En el caso de los correos electrónicos, puede reaccionar ante los mensajes en los que se ha hecho clic, se han enviado, se han abierto o no se han podido realizar.

También puede utilizar este mecanismo para realizar una acción cuando no haya reacción a sus mensajes. Para ello, cree una segunda ruta paralela a la actividad de reacción y añada una actividad de espera. Si no hay ninguna reacción durante el periodo definido en la actividad de espera, se elige la segunda ruta. Puede optar por enviar, por ejemplo, un mensaje de seguimiento.

Tenga en cuenta que solo puede utilizar una actividad de reacción en el lienzo si antes hay una actividad de correo electrónico, push o SMS.

Consulte [Acerca de las actividades de acción](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estos son los diferentes pasos para configurar los eventos de reacción:

1. Agregue un **[!UICONTROL Label]** a la reacción. Este paso es opcional.
1. En la lista desplegable, seleccione la actividad de acción a la que desee reaccionar. Puede seleccionar cualquier actividad de acción posicionada en los pasos anteriores de la ruta.
1. En función de la acción seleccionada (un correo electrónico, un SMS o una notificación push), elija a qué desea reaccionar.
1. Puede definir una condición como paso opcional. Por ejemplo, después de una acción por correo electrónico, puede decidir crear dos rutas, una con un evento de reacción para rastrear clics solo para VIP clientes y otra con un evento de reacción para rastrear los clics realizados por mujeres.

>[!NOTE]
>
>Los eventos de reacción funcionan con Adobe Campaign Standard, tanto si se implementan en servidores AWS como Azure.
>
>Los eventos de reacción no pueden rastrear correos electrónicos, SMS o acciones push que se producen en un recorrido diferente.
>
>Los eventos de reacción rastrean clics en vínculos del tipo &quot;rastreados&quot; (consulte esta [página](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). No se tienen en cuenta los vínculos de páginas espejo y de baja de suscripción.

>[!IMPORTANT]
>
>Los clientes de correo electrónico como Gmail permiten el bloqueo de imágenes. Las aperturas de correo electrónico se rastrean utilizando una imagen de 0 píxeles incluida en el correo electrónico. Si las imágenes están bloqueadas, las aperturas por correo electrónico no se tienen en cuenta.
