---
product: adobe campaign
title: Acerca de las actividades de eventos
description: Más información sobre las actividades de eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: fca24f7dd0f9170fa209474f270a4c0fb4080c03
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Acerca de las actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (vea [esta página](../event/about-events.md)) se muestran todos en la primera categoría de la paleta, a la izquierda de la pantalla.

![](../assets/journey43.png)

Inicie siempre el recorrido arrastrando y soltando una actividad de evento. También puede hacer doble clic en él.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede usar el campo **[!UICONTROL Label]** para agregar un sufijo al nombre del evento que aparecerá debajo de su actividad en el lienzo. Esto resulta útil para identificar los eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilita la depuración en caso de errores y la lectura de los informes.

![](../assets/journey33.png)

## Escucha de eventos durante un evento específico {#listening}

Una actividad de evento colocada en el recorrido escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe configurar un tiempo de espera para el evento.

El recorrido escuchará el evento durante el tiempo especificado en el tiempo de espera. Si se recibe un evento durante ese período, la persona fluirá en la ruta del evento. Si no es así, el cliente fluirá a la ruta de tiempo de espera si está definida o continuará ese recorrido. Si no se define ninguna ruta de tiempo de espera, la configuración de tiempo de espera actuará como una actividad de espera, lo que hace que el perfil espere durante un período de tiempo, que podría detenerse si se produce un evento antes del final de esa espera. Si desea que los perfiles se excluyan de ese recorrido después del tiempo de espera, deberá establecer una ruta de tiempo de espera.

Para configurar un tiempo de espera para un evento, siga estos pasos:

1. Active la opción **[!UICONTROL Enable the event timeout]** desde las propiedades del evento.

1. Especifique la cantidad de tiempo que el recorrido esperará el evento.

1. Si desea enviar a las personas a una ruta de tiempo de espera cuando no se reciba ningún evento dentro del tiempo de espera especificado, habilite la opción **[!UICONTROL Set the timeout path]**. Si esta opción no está habilitada, el recorrido continuará para el individuo una vez que se alcance el tiempo de espera.

   ![](../assets/event-timeout.png)

En este ejemplo, el recorrido envía una primera notificación push de bienvenida a un cliente. A continuación, envía una notificación push de descuento en la comida solo si el cliente entra en el restaurante dentro del día siguiente. Por lo tanto, configuramos el evento del restaurante con un tiempo de espera de 1 día:

* Si el evento del restaurante se recibe menos de 1 día después de la notificación push de bienvenida, se envía la actividad push de descuento en la comida.
* Si no se recibe ningún evento de restaurante al día siguiente, la persona pasa por la ruta de tiempo de espera.

Tenga en cuenta que si desea configurar un tiempo de espera en varios eventos colocados después de una actividad de **[!UICONTROL Wait]**, solo debe configurar el tiempo de espera en uno de estos eventos.

El tiempo de espera se aplicará a todos los eventos colocados después de la actividad **[!UICONTROL Wait]**. Si no se recibe ningún evento antes del tiempo de espera especificado, los individuos fluirán en una sola ruta de tiempo de espera o continuarán ese recorrido a través de la rama que sale de la actividad en la que se han definido esos ajustes de tiempo de espera.

![](../assets/event-timeout-group.png)
