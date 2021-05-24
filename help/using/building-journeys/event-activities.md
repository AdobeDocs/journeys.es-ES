---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de las actividades de eventos
description: Descubra más información sobre las actividades de eventos
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: db7567f7f3333ad69015d07991158ce5b8f01af5
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---

# Acerca de las actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (consulte [esta página](../event/about-events.md)) se muestran en la primera categoría de la paleta, en la parte izquierda de la pantalla.

![](../assets/journey43.png)

Inicie siempre el recorrido arrastrando y soltando una actividad de evento. También puede hacer doble clic en él.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de la actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede utilizar el campo **[!UICONTROL Label]** para agregar un sufijo al nombre del evento que aparecerá debajo de la actividad en el lienzo. Esto resulta útil para identificar los eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilitará la depuración en caso de errores y facilitará la lectura de los informes.

![](../assets/journey33.png)

## Escucha de eventos durante un tiempo específico

Una actividad de evento ubicada en el recorrido escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe configurar un tiempo de espera para el evento.

El recorrido escuchará el evento durante el tiempo especificado en el tiempo de espera. Si se recibe un evento durante ese periodo, la persona fluirá en la ruta del evento. Si no es así, el cliente pasará a una ruta de tiempo de espera o finalizará su recorrido.

Para configurar un tiempo de espera para un evento, siga estos pasos:

1. Active la opción **[!UICONTROL Enable the event timeout]** en las propiedades de evento.

1. Especifique la cantidad de tiempo que el recorrido esperará al evento.

1. Si desea enviar a las personas a una ruta de tiempo de espera cuando no se reciba ningún evento dentro del tiempo de espera especificado, habilite la opción **[!UICONTROL Set the timeout path]**. Si esta opción no está activada, el recorrido finalizará para el individuo una vez que se alcance el tiempo de espera.

   ![](../assets/event-timeout.png)

En este ejemplo, el recorrido envía una primera notificación push de bienvenida a un cliente. A continuación, envía una notificación push de descuento en la comida solo si el cliente entra en el restaurante en el día siguiente. Por lo tanto, configuramos el evento del restaurante con un tiempo de espera de 1 día:

* Si el evento del restaurante se recibe menos de 1 día después de la notificación push de bienvenida, se envía la actividad push de descuento por comida.
* Si no se recibe ningún evento de restaurante en el día siguiente, la persona pasa por la ruta de tiempo de espera.

Tenga en cuenta que si desea configurar un tiempo de espera en varios eventos posicionados después de una actividad **[!UICONTROL Wait]** , debe configurar el tiempo de espera solo en uno de estos eventos.

El tiempo de espera se aplicará a todos los eventos posicionados después de la actividad **[!UICONTROL Wait]**. Si no se recibe ningún evento antes del tiempo de espera especificado, las personas fluirán en una única ruta de tiempo de espera o finalizarán su recorrido.

![](../assets/event-timeout-group.png)
