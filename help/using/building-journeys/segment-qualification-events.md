---
product: adobe campaign
title: Eventos de cualificación de segmentos
description: Obtenga información sobre los eventos de calificación de segmentos
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 1%

---

# Eventos de cualificación de segmentos {#segment-qualification}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._



## Acerca de los eventos de calificación de segmentos{#about-segment-qualification}

Esta actividad permite al recorrido escuchar las entradas y salidas de perfiles en segmentos de Adobe Experience Platform para que los individuos entren o avancen en un recorrido. Para obtener más información sobre la creación de segmentos, consulte esta [sección](../segment/about-segments.md).

Supongamos que tiene un segmento llamado &quot;cliente plata&quot;. Con esta actividad, puede hacer que todos los clientes nuevos de Silver Ingresen a un recorrido y les envíen una serie de mensajes personalizados.

Este tipo de evento se puede colocar como primer paso o más tarde en el recorrido.

>[!IMPORTANT]
>
>Tenga en cuenta que los segmentos de Adobe Experience Platform se calculan una vez al día (**lote** segmentos) o en tiempo real (**transmitidos** segmentos, utilizando la opción Audiencias de alta frecuencia de Adobe Experience Platform).
>
>Si el segmento seleccionado se transmite, las personas que pertenecen a este segmento potencialmente ingresarán al recorrido en tiempo real. Si el segmento es por lotes, las personas recién cualificadas para este segmento potencialmente ingresarán al recorrido cuando el cálculo del segmento se ejecute en Adobe Experience Platform.


1. Despliegue la categoría **[!UICONTROL Events]** y suelte una actividad **[!UICONTROL Segment qualification]** en el lienzo.

   ![](../assets/segment5.png)

1. Agregue un(a) **[!UICONTROL Label]** a la actividad. Este paso es opcional.

1. Haga clic en el campo **[!UICONTROL Segment]** y seleccione los segmentos que desea aprovechar.

   >[!NOTE]
   >
   >Tenga en cuenta que puede personalizar las columnas mostradas en la lista y ordenarlas.

   ![](../assets/segment6.png)

   Una vez agregado el segmento, el botón **[!UICONTROL Copy]** le permite copiar su nombre e ID:

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. En el campo **[!UICONTROL Behaviour]**, elija si desea escuchar las entradas del segmento, las salidas o ambas cosas.

   >[!NOTE]
   >
   >Tenga en cuenta que **[!UICONTROL Enter]** y **[!UICONTROL Exit]** corresponden a los estados de participación de segmentos **Realizado** y **Salido** de Adobe Experience Platform. Para obtener más información sobre cómo evaluar un segmento, consulte la [documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=es#interpret-segment-results).

1. Seleccione un área de nombres. Esto solo es necesario si el evento se coloca como el primer paso del recorrido.

   ![](../assets/segment7.png)

La carga útil contiene la siguiente información de contexto, que puede utilizar en condiciones y acciones:

* el comportamiento (entrada, salida)
* la marca de tiempo de la calificación
* el id del segmento

Al utilizar el editor de expresiones en una condición o acción que sigue a una actividad **[!UICONTROL Segment qualification]**, tiene acceso al nodo **[!UICONTROL SegmentQualification]**. Puede elegir entre **[!UICONTROL Last qualification time]** y **[!UICONTROL status]** (entrada o salida).

Consulte [Actividad de condición](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Un nuevo recorrido que incluye un evento de calificación de segmentos está en funcionamiento diez minutos después de su publicación. Este intervalo de tiempo corresponde al intervalo de actualización de caché del servicio dedicado. Por lo tanto, debe esperar diez minutos antes de utilizar este recorrido.

## Prácticas recomendadas {#best-practices-segments}

La actividad **[!UICONTROL Segment Qualification]** permite la entrada inmediata en recorridos de personas que cumplen o no los requisitos de un segmento de Adobe Experience Platform.

La velocidad de recepción de esta información es alta. Las mediciones realizadas muestran una velocidad de 10 000 eventos recibidos por segundo. Como resultado, debe asegurarse de comprender cómo pueden producirse los picos de entrada, cómo evitarlos y cómo preparar su recorrido para ellos.

### Segmentos por lotes{#batch-speed-segment-qualification}

Cuando utilice la calificación de segmentos para un segmento de lote, tenga en cuenta que se producirá un pico de entrada en el momento del cálculo diario. El tamaño del pico dependerá del número de individuos que entren (o salgan) del segmento diariamente.

Además, si el segmento de lote se crea recientemente y se utiliza inmediatamente en un recorrido, el primer lote de cálculo puede hacer que un gran número de personas entren en el recorrido.

### Segmentos transmitidos{#streamed-speed-segment-qualification}

Cuando se utiliza la calificación de segmentos para segmentos transmitidos, hay menos riesgo de obtener grandes picos de entradas/salidas debido a la evaluación continua del segmento. Sin embargo, si la definición del segmento conduce a que un gran volumen de clientes cumpla los requisitos al mismo tiempo, puede haber un pico también.

Para obtener más información sobre la segmentación de transmisión, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html?lang=es#api)

### Cómo evitar sobrecargas{#overloads-speed-segment-qualification}

Estas son algunas prácticas recomendadas que le ayudarán a evitar la sobrecarga de sistemas aprovechada en los recorridos (fuentes de datos, acciones personalizadas, acciones de Adobe Campaign Standard).

No utilice, en una actividad **[!UICONTROL Segment Qualification]**, un segmento por lotes inmediatamente después de su creación. Evitará el primer pico de cálculo. Tenga en cuenta que si está a punto de usar un segmento que nunca se ha calculado, aparecerá una advertencia amarilla en el lienzo de recorrido.

![](../assets/segment-error.png)

Establezca una regla de límite para las fuentes de datos y las acciones utilizadas en los recorridos para evitar sobrecargarlos (consulte esta [sección](../api/capping.md)). Tenga en cuenta que la regla de límite no tiene reintento. Si necesita volver a intentarlo, debe utilizar una ruta alternativa en el recorrido marcando la casilla **[!UICONTROL Add an alternative path in case of a timeout or an error]** en condiciones o acciones.

Antes de usar el segmento en un recorrido de producción, evalúe siempre primero el volumen de personas que cumplen los requisitos para este segmento todos los días. Para ello, puede comprobar la sección **[!UICONTROL Segments]** en Adobe Experience Platform y ver el gráfico a la derecha.

![](../assets/segment-overload.png)
