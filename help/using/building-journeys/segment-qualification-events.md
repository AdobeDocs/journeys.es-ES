---
product: adobe campaign
title: Eventos de calificación de segmentos
description: Descubra más información sobre los eventos de calificación de segmentos
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# Eventos de calificación de segmentos {#segment-qualification}

## Acerca de los eventos de calificación de segmentos{#about-segment-qualification}

Esta actividad permite que el recorrido escuche las entradas y salidas de perfiles en segmentos de Adobe Experience Platform para que los individuos entren o avancen en un recorrido. Para obtener más información sobre la creación de segmentos, consulte esta [sección](../segment/about-segments.md).

Supongamos que tiene un segmento &quot;cliente plata&quot;. Con esta actividad, puede hacer que todos los clientes nuevos de plata introduzcan un recorrido y envíen una serie de mensajes personalizados.

Este tipo de evento se puede posicionar como el primer paso o posterior en el recorrido.

>[!IMPORTANT]
>
>Tenga en cuenta que los segmentos de Adobe Experience Platform se calculan una vez al día (**batch** segmentos) o en tiempo real (**transmitido** con la opción Audiencias de alta frecuencia de Adobe Experience Platform).
>
>Si el segmento seleccionado se transmite, las personas que pertenezcan a este segmento potencialmente entrarán en el recorrido en tiempo real. Si el segmento es por lotes, las personas que acaben de calificar para este segmento potencialmente introducirán el recorrido cuando se ejecute el cálculo del segmento en Adobe Experience Platform.


1. Despliegue el **[!UICONTROL Events]** categoría y suelte a **[!UICONTROL Segment qualification]** actividad en el lienzo.

   ![](../assets/segment5.png)

1. Agregue un **[!UICONTROL Label]** a la actividad . Este paso es opcional.

1. Haga clic en el **[!UICONTROL Segment]** y seleccione los segmentos que desea aprovechar.

   >[!NOTE]
   >
   >Tenga en cuenta que puede personalizar las columnas mostradas en la lista y ordenarlas.

   ![](../assets/segment6.png)

   Una vez agregado el segmento, la variable **[!UICONTROL Copy]** permite copiar su nombre y su ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. En el **[!UICONTROL Behaviour]** , elija si desea escuchar las entradas de segmentos, las salidas o ambas.

   >[!NOTE]
   >
   >Tenga en cuenta que **[!UICONTROL Enter]** y **[!UICONTROL Exit]** corresponde a la variable **Realizado** y **Salido** estados de participación de segmentos desde Adobe Experience Platform. Para obtener más información sobre cómo evaluar un segmento, consulte la [Documentación del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Seleccione un espacio de nombres. Esto solo es necesario si el evento se coloca como el primer paso del recorrido.

   ![](../assets/segment7.png)

La carga útil contiene la siguiente información de contexto, que puede utilizar en condiciones y acciones:

* el comportamiento (entrada, salida)
* la marca de tiempo de la calificación
* el id de segmento

Cuando se utiliza el editor de expresiones en una condición o acción que sigue a una **[!UICONTROL Segment qualification]** actividad, tiene acceso a la **[!UICONTROL SegmentQualification]** nodo . Puede elegir entre la variable **[!UICONTROL Last qualification time]** y **[!UICONTROL status]** (entrar o salir).

Consulte [Actividad de condición](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Un nuevo recorrido que incluye un evento de calificación de segmentos funciona diez minutos después de publicarlo. Este intervalo de tiempo corresponde al intervalo de actualización de la caché del servicio dedicado. Por lo tanto, debe esperar diez minutos antes de utilizar este recorrido.

## Prácticas recomendadas {#best-practices-segments}

La variable **[!UICONTROL Segment Qualification]** permite la entrada inmediata en recorridos de personas que se han clasificado o descalificado de un segmento de Adobe Experience Platform.

La velocidad de recepción de esta información es alta. Las mediciones realizadas muestran una velocidad de 10 000 eventos recibidos por segundos. Por tanto, es importante saber cómo pueden producirse los picos de entrada, cómo evitarlos y cómo preparar el recorrido para ellos.

### Segmentos por lotes{#batch-speed-segment-qualification}

Cuando utilice la calificación de segmentos para un segmento por lotes, tenga en cuenta que se producirá un pico de entrada en el momento del cálculo diario. El tamaño del pico dependerá del número de personas que entren (o salgan) en el segmento a diario.

Además, si el segmento por lotes se crea recientemente y se utiliza inmediatamente en un recorrido, el primer lote de cálculo puede hacer que un número muy grande de personas entre en el recorrido.

### Segmentos transmitidos{#streamed-speed-segment-qualification}

Al utilizar la calificación de segmentos para segmentos transmitidos, existe menos riesgo de obtener grandes picos de entradas y salidas debido a la evaluación continua del segmento. Sin embargo, si la definición del segmento conduce a que un gran volumen de clientes se califique al mismo tiempo, también podría haber un pico.

Para obtener más información sobre la segmentación de flujo continuo, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Cómo evitar sobrecargas{#overloads-speed-segment-qualification}

Estas son algunas prácticas recomendadas que ayudarán a evitar la sobrecarga de sistemas apalancados en recorridos (fuentes de datos, acciones personalizadas, acciones de Adobe Campaign Standard).

No use, en **[!UICONTROL Segment Qualification]** actividad, un segmento por lotes inmediatamente después de su creación. Evitará el primer pico de cálculo. Tenga en cuenta que habrá una advertencia amarilla en el lienzo de recorrido si está a punto de usar un segmento que nunca se ha calculado.

![](../assets/segment-error.png)

Establezca una regla de límite para las fuentes de datos y las acciones utilizadas en los recorridos para evitar sobrecargarlas (consulte esta [sección](../api/capping.md)). Tenga en cuenta que la regla de restricción no tiene reintento. Si necesita volver a intentarlo, debe utilizar una ruta alternativa en el recorrido marcando la casilla **[!UICONTROL Add an alternative path in case of a timeout or an error]** en condiciones o acciones.

Antes de usar el segmento en un recorrido de producción, evalúe siempre primero el volumen de personas que cumplen los requisitos para este segmento todos los días. Para ello, puede marcar la **[!UICONTROL Segments]** en Adobe Experience Platform y observe el gráfico en el lado derecho.

![](../assets/segment-overload.png)
