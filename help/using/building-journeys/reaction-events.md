---
product: adobe campaign
title: Eventos de reacción
description: Más información sobre los eventos de reacción
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 2%

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
1. Puede definir un tiempo de espera de evento (entre 40 segundos y 30 días) y una ruta de tiempo de espera. Esto creará una segunda ruta para las personas que no reaccionaron dentro de la duración definida. Al probar un recorrido que utiliza un evento de reacción, el modo de prueba **[!UICONTROL Wait time]** predeterminado y el valor mínimo es de 40 segundos. Consulte [esta sección](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Los eventos de reacción funcionan con Adobe Campaign Standard, tanto si se implementan en servidores AWS como Azure.
>
>Los eventos de reacción no pueden rastrear correos electrónicos, SMS o acciones push que se producen en un recorrido diferente.
>
>Los eventos de reacción rastrean clics en vínculos del tipo &quot;rastreados&quot; (consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)). No se tienen en cuenta los vínculos de páginas espejo y de baja de suscripción.

>[!IMPORTANT]
>
>Los clientes de correo electrónico como Gmail permiten el bloqueo de imágenes. Las aperturas de correo electrónico se rastrean utilizando una imagen de 0 píxeles incluida en el correo electrónico. Si las imágenes están bloqueadas, las aperturas por correo electrónico no se tienen en cuenta.
