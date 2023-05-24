---
product: adobe campaign
title: Acerca de las actividades de eventos
description: Más información sobre las actividades de eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 5b09ed456b6a9645dbb7897481317d3904e29d31
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Acerca de las actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (consulte [esta página](../event/about-events.md)) se muestran todos en la primera categoría de la paleta, en el lado izquierdo de la pantalla.

![](../assets/journey43.png)

Inicie siempre el recorrido arrastrando y soltando una actividad de evento. También puede hacer doble clic en él.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede utilizar la variable **[!UICONTROL Label]** para añadir un sufijo al nombre del evento que aparecerá bajo su actividad en el lienzo. Esto resulta útil para identificar los eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilita la depuración en caso de errores y la lectura de los informes.

![](../assets/journey33.png)

## Escucha de eventos durante un tiempo específico

Una actividad de evento colocada en el recorrido escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe configurar un tiempo de espera para el evento.

El recorrido escuchará el evento durante el tiempo especificado en el tiempo de espera. Si se recibe un evento durante ese período, la persona fluirá en la ruta del evento. Si no es así, el cliente fluirá a una ruta de tiempo de espera o finalizará su recorrido.

Para configurar un tiempo de espera para un evento, siga estos pasos:

1. Activar el **[!UICONTROL Enable the event timeout]** en las propiedades de evento.

1. Especifique la cantidad de tiempo que el recorrido esperará el evento.

1. Si desea enviar a las personas a una ruta de tiempo de espera cuando no se reciba ningún evento dentro del tiempo de espera especificado, habilite la opción **[!UICONTROL Set the timeout path]** opción. Si esta opción no está habilitada, el recorrido finalizará para el individuo una vez que se alcance el tiempo de espera.

   ![](../assets/event-timeout.png)

En este ejemplo, el recorrido envía una primera notificación push de bienvenida a un cliente. A continuación, envía una notificación push de descuento en la comida solo si el cliente entra en el restaurante dentro del día siguiente. Por lo tanto, configuramos el evento del restaurante con un tiempo de espera de 1 día:

* Si el evento del restaurante se recibe menos de 1 día después de la notificación push de bienvenida, se envía la actividad push de descuento en la comida.
* Si no se recibe ningún evento de restaurante al día siguiente, la persona pasa por la ruta de tiempo de espera.

Tenga en cuenta que si desea configurar un tiempo de espera en varios eventos colocados después de una **[!UICONTROL Wait]** actividad, solo debe configurar el tiempo de espera en uno de estos eventos.

El tiempo de espera se aplicará a todos los eventos colocados después de **[!UICONTROL Wait]** actividad. Si no se recibe ningún evento antes del tiempo de espera especificado, los individuos fluirán a una sola ruta de tiempo de espera o finalizarán su recorrido.

![](../assets/event-timeout-group.png)
