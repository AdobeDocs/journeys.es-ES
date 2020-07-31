---
title: actividad del activador de segmentos
description: Más información sobre el activador de segmentos
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
source-git-commit: b66cdb31b62b4627ff7378e48879ffadfedda5cb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# actividad del activador de segmentos {#segment-trigger-activity}

## Acerca de la actividad Activador de segmentos {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Si hay una actividad de acción lista para usar de Adobe Campaign Standard en el lienzo en tiempo de publicación o en tiempo de activación del modo de prueba, el viaje se reducirá a 13 entradas por segundo. <br>Si no hay ninguna actividad de acción lista para usar en Adobes Campaign Standard en el lienzo en tiempo de publicación o en tiempo de activación del modo de prueba, el viaje se reducirá a 1000 eventos por segundo.

La actividad Activador de segmentos le permite hacer que todas las personas que pertenecen a un segmento de Adobe Experience Platform entren en un viaje. La entrada en un viaje puede realizarse una vez o de forma regular.

Supongamos que tiene un segmento de clientes Gold en Adobe Experience Platform. Con la actividad Activador de segmentos, puede hacer que todas las personas pertenecientes al segmento de clientes Gold participen en un viaje y que fluyan en viajes individualizados que aprovechen todas las funcionalidades del viaje: condiciones, temporizadores, eventos, acciones.

## Configuring the activity {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Debido a las latencias de exportación de segmentos, no es posible iniciar un viaje basado en segmentos en un intervalo de tiempo más corto que 1 hora.

1. Despliegue la **[!UICONTROL Orchestration]** categoría y suelte una **[!UICONTROL Segment Trigger]** actividad en el lienzo.

   La actividad debe situarse como el primer paso de un viaje.

1. Configure the activity **[!UICONTROL Scheduler type]**.

   De forma predeterminada, el segmento entrará en el viaje **[!UICONTROL As soon as possible]**, es decir, 1 hora después de que se publique el viaje. Si desea que el segmento introduzca el viaje en una fecha/hora específica o de forma recurrente, seleccione la opción deseada en la lista.

   En caso de viajes recurrentes, también puede definir el inicio y el final del viaje.

   ![](../assets/segment-trigger-schedule.png)

1. En el **[!UICONTROL Segment]** campo, elija el segmento de Adobe Experience Platform que entrará en el viaje y haga clic en **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. En el **[!UICONTROL Namespace]** campo, elija la Área de nombres que desee utilizar para identificar a los individuos. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Las personas que pertenecen a un segmento que no tiene la identidad seleccionada (Área de nombres) entre sus distintas identidades no pueden entrar en el viaje.

1. Haga clic en **[!UICONTROL Ok]** para confirmar. Luego puede aprovechar las actividades disponibles para construir su viaje.

1. Una vez que el viaje esté listo, puede probarlo potencialmente (consulte [Prueba del viaje](../building-journeys/testing-the-journey.md)).

   Cuando se activa el modo de prueba en un viaje que comienza con una **[!UICONTROL Segment Trigger]** actividad, se seleccionan aleatoriamente 100 perfiles de prueba entre los perfiles cualificados para el segmento seleccionado. Los registros de prueba le permitirán ver la ruta de los individuos en el viaje y los posibles errores encontrados (consulte [Visualización de los registros](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Tenga en cuenta que no podrá ver a las 100 personas que siguen el viaje utilizando la función de flujo visual existente en los viajes unitarios.

1. A continuación, puede publicar su viaje (consulte [Publicación del viaje](../building-journeys/publishing-the-journey.md)). Las personas que pertenezcan al segmento entrarán en el viaje en la fecha y hora especificadas en el Planificador de actividad del activador de segmentos.

   >[!IMPORTANT]
   >
   >Tenga en cuenta que los segmentos de Adobe Experience Platform se calculan una vez al día (segmentos de **lote** ) o en tiempo real (segmentos de **flujo** ).
   >
   >Si se transmite el segmento seleccionado, los individuos pertenecientes a este segmento potencialmente entrarán en el viaje en tiempo real. Si el segmento es por lotes, las personas recién calificadas para este segmento posiblemente entrarán en el viaje cuando el cálculo del segmento se ejecute en el Adobe Experience Platform.
