---
product: adobe campaign
title: Eventos de reacciones
description: Más información sobre los eventos de reacción
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---

# Eventos de reacción {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._



Entre las diferentes actividades de evento disponibles en la paleta, se encuentra el evento integrado **[!UICONTROL Reactions]**. Esta actividad le permite reaccionar al seguimiento de datos relacionados con un mensaje enviado con actividades de correo electrónico, SMS o push dentro del mismo recorrido. Esta información proviene de la mensajería transaccional de Adobe Campaign Standard. Capturamos esta información en tiempo real en el momento en que se comparte con Adobe Experience Platform. Para las notificaciones push, puede reaccionar a los mensajes en los que se ha hecho clic, enviados o fallidos. En el caso de los mensajes SMS, puede reaccionar a los mensajes enviados o fallidos. En el caso de los correos electrónicos, puede reaccionar a los mensajes en los que se ha hecho clic, enviados, abiertos o fallidos.

También puede utilizar este mecanismo para realizar una acción cuando no haya ninguna reacción a los mensajes. Para ello, cree una segunda ruta paralela a la actividad de reacción y añada una actividad de espera. Si no hay ninguna reacción durante el periodo definido en la actividad de espera, se elige la segunda ruta. Puede elegir enviar, por ejemplo, un mensaje de seguimiento.

Tenga en cuenta que solo puede utilizar una actividad de reacción en el lienzo si hay una actividad de correo electrónico, push o SMS antes de.

Consulte [Acerca de las actividades de acción](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estos son los pasos para configurar los eventos de reacción:

1. Agregar **[!UICONTROL Label]** a la reacción. Este paso es opcional.
1. En la lista desplegable, seleccione la actividad de acción a la que desee reaccionar. Puede seleccionar cualquier actividad de acción colocada en los pasos anteriores de la ruta.
1. Según la acción seleccionada (un correo electrónico, SMS o una notificación push), elija a qué desea reaccionar.
1. Puede definir un tiempo de espera de evento (entre 40 segundos y 30 días) y una ruta de tiempo de espera. Esto creará una segunda ruta para las personas que no reaccionaron dentro de la duración definida. Al probar un recorrido que utiliza un evento de reacción, el modo de prueba **[!UICONTROL Wait time]** tiene un valor predeterminado y mínimo de 40 segundos. Consulte [esta sección](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Los eventos de reacción funcionan con Adobe Campaign Standard, tanto si se implementa en servidores de AWS como de Azure.
>
>Los eventos de reacción no pueden rastrear acciones de correo electrónico, SMS o push que se produzcan en un recorrido diferente.
>
>Los eventos de reacción rastrean los clics en vínculos del tipo &quot;rastreados&quot; (consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)). No se tienen en cuenta los vínculos de baja de suscripción y de página espejo.

>[!IMPORTANT]
>
>Los clientes de correo electrónico como Gmail permiten el bloqueo de imágenes. El seguimiento de las aperturas de los correos electrónicos se realiza mediante una imagen de 0 píxeles incluida en el correo electrónico. Si las imágenes están bloqueadas, las aperturas de correo electrónico no se tendrán en cuenta.
