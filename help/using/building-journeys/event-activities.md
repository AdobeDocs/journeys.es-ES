---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de las actividades de eventos
description: Más información sobre actividades de eventos
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# Acerca de las actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (consulte [esta página](../event/about-events.md)) se muestran en la primera categoría de la paleta, en la parte izquierda de la pantalla.

![](../assets/journey43.png)

Siempre inicio el viaje arrastrando y soltando una actividad de evento. También puede hacer clic con el doble.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede utilizar el **[!UICONTROL Label]** campo para agregar un sufijo al nombre del evento que aparecerá debajo de la actividad en el lienzo. Esto resulta útil para identificar sus eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilitará la depuración en caso de errores y facilitará la lectura de los informes.

![](../assets/journey33.png)

## Escuchar eventos durante un tiempo específico

Una actividad de evento situada en el viaje escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe configurar un tiempo de espera para el evento.

El viaje escuchará el evento durante el tiempo especificado en el tiempo de espera. Si se recibe un evento durante ese período, la persona fluirá por la ruta del evento. Si no es así, el cliente pasará a una ruta de tiempo de espera o finalizará su viaje.

Para configurar un tiempo de espera para un evento, siga estos pasos:

1. Active la **[!UICONTROL Enable the event timeout]** opción desde las propiedades de evento.

1. Especifique la cantidad de tiempo que el viaje esperará para el evento.

1. Si desea enviar a los individuos a una ruta de tiempo de espera cuando no se recibe ningún evento dentro del tiempo de espera especificado, habilite la **[!UICONTROL Set the timeout path]** opción. Si esta opción no está habilitada, el viaje finalizará para el individuo una vez que se alcance el tiempo de espera.

   ![](../assets/event-timeout.png)

En este ejemplo, el viaje envía un primer mensaje de bienvenida a un cliente. Luego envía un descuento por comida solamente si el cliente entra al restaurante en el día siguiente. Por lo tanto, configuramos el evento con un tiempo de espera de 1 día:

* Si el evento del restaurante se recibe menos de 1 día después de la entrada de bienvenida, se envía la actividad de descuento por comida.
* Si no se recibe ningún evento de restaurante en el día siguiente, la persona pasa por la ruta de tiempo de espera.

Tenga en cuenta que si desea configurar un tiempo de espera en varios eventos posicionados después de una **[!UICONTROL Wait]** actividad, debe configurar el tiempo de espera solo en uno de estos eventos.

El tiempo de espera se aplicará a todos los eventos colocados después de la **[!UICONTROL Wait]** actividad. Si no se recibe ningún evento después del tiempo de espera especificado, los individuos fluirán en una única ruta de tiempo de espera o finalizarán su viaje.

![](../assets/event-timeout-group.png)
