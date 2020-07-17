---
title: Acerca de las actividades de eventos
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Acerca de las actividades de eventos {#concept_rws_1rt_52b}

Los eventos configurados por el usuario técnico (véase [](../event/about-events.md)) se muestran en la primera categoría de la paleta, en la parte izquierda de la pantalla.

![](../assets/journey43.png)

Siempre inicio el viaje arrastrando y soltando una actividad de evento. También puede hacer clic con el doble.

![](../assets/journey44.png)

Al hacer clic en la actividad de evento en el lienzo, se muestra el panel de configuración de actividad. De forma predeterminada, cuando se utiliza el mismo evento varias veces, se agrega un número incrementado al nombre del evento en el lienzo. Además, puede utilizar el **[!UICONTROL Label]** campo para agregar un sufijo al nombre del evento que aparecerá debajo de la actividad en el lienzo. Esto resulta útil para identificar sus eventos en el lienzo, especialmente si utiliza el mismo evento varias veces. También facilitará la depuración en caso de errores y facilitará la lectura de los informes.

![](../assets/journey33.png)

## Uso avanzado: eventos con una espera en paralelo{#section_vxv_h25_pgb}

**¿Cómo se puede escuchar un evento sólo durante un tiempo determinado?**

Una actividad de evento situada en el viaje escucha eventos indefinidamente. Para escuchar un evento solo durante un tiempo determinado, debe agregar una actividad de espera paralela a la ruta de evento. El viaje escuchará el evento durante el tiempo especificado en la actividad de espera. Si se recibe un evento durante ese período, la persona fluirá por la ruta del evento. Si no es así, el cliente irá a la ruta de espera.

Por ejemplo, se ha enviado una primera notificación push de bienvenida a un cliente y se desea enviar una notificación push de descuento solo si el cliente entra en el restaurante en las siguientes 6 horas. Para ello, se crea un segundo camino (paralelo al evento uno) con una actividad de espera de 6 horas. Si el evento del restaurante se recibe menos de 6 horas después de la entrada de bienvenida, se envía la actividad push de descuento por comida. Si no se recibe ningún evento en las siguientes 6 horas, la persona pasa por el camino de espera.

![](../assets/journeyuc2_31.png)
