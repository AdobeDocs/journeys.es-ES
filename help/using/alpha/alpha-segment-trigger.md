---
product: adobe campaign
solution: Journey Orchestration
title: Leer Actividad de segmentos
description: Obtenga más información sobre la actividad Leer segmento.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 4%

---


# Leer Actividad de segmentos {#segment-trigger-activity}

## Acerca de la actividad Leer segmento {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Si hay una actividad de acción lista para usar de Adobe Campaign Standard en el lienzo en tiempo de publicación o en tiempo de activación del modo de prueba, el viaje se reducirá a 13 entradas por segundo. De lo contrario, el viaje se reducirá a 1000 eventos por segundo.

La actividad Leer segmento le permite hacer que todas las personas que pertenecen a un segmento de Adobe Experience Platform participen en un viaje. La entrada en un recorrido puede realizarse una vez o de forma regular.

Supongamos que tiene un segmento de clientes Gold en Adobe Experience Platform. Con la actividad Leer segmento, puede hacer que todas las personas pertenecientes al segmento de clientes Gold participen en un viaje y que fluyan en viajes individualizados que aprovechen todas las funcionalidades del viaje: condiciones, temporizadores, eventos, acciones.

>[!NOTE]
>
>No puede tener una actividad de salto y **segmento de lectura** en el mismo viaje. No puede saltar a un viaje que inicio con un evento **Leer segmento**.

## Configuración de la actividad {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Debido a las latencias de exportación de segmentos, no es posible iniciar un viaje basado en segmentos en un intervalo de tiempo más corto que 1 hora.

1. Despliegue la categoría **[!UICONTROL Orchestration]** y suelte una actividad **[!UICONTROL Read Segment]** en el lienzo.

   La actividad debe situarse como el primer paso de un viaje.

1. Añada un **[!UICONTROL Label]** en la actividad (opcional).

1. En el campo **[!UICONTROL Segment]**, elija el segmento de Adobe Experience Platform que entrará en el viaje y haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Tenga en cuenta que puede personalizar las columnas que se muestran en la lista y ordenarlas.

   ![](../assets/segment-trigger-segment-selection.png)

   Una vez agregado el segmento, el botón **[!UICONTROL Copy]** le permite copiar su nombre e ID:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. En el campo **[!UICONTROL Namespace]**, elija la Área de nombres que desee utilizar para identificar a los individuos. Para obtener más información sobre Áreas de nombres, consulte [esta sección](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Las personas que pertenecen a un segmento que no tiene la identidad seleccionada (Área de nombres) entre sus distintas identidades no pueden entrar en el viaje.

1. La actividad **[!UICONTROL Read Segment]** permite especificar la hora a la que el segmento entrará en el viaje. Para ello, haga clic en el vínculo **[!UICONTROL Edit journey schedule]** para acceder a las propiedades del viaje y, a continuación, configure el campo **[!UICONTROL Scheduler type]**.

   ![](../assets/segment-trigger-schedule.png)

   De forma predeterminada, los segmentos introducen el viaje **[!UICONTROL As soon as possible]**, es decir, 1 hora después de publicar el viaje. Si desea que el segmento introduzca el viaje en una fecha/hora específica o de forma recurrente, seleccione el valor deseado en la lista.

   >[!NOTE]
   >
   >Tenga en cuenta que la sección **[!UICONTROL Schedule]** sólo está disponible cuando se ha colocado una actividad **[!UICONTROL Read Segment]** en el lienzo.

   ![](../assets/segment-trigger-properties.png)

## Prueba y publicación del viaje {#testing-publishing}

La actividad **[!UICONTROL Read Segment]** le permite probar el viaje en un perfil unitario o en 100 perfiles de prueba aleatorios seleccionados entre los perfiles calificados para el segmento.

Para ello, active el modo de prueba y, a continuación, seleccione la opción que desee en el panel izquierdo.

![](../assets/segment-trigger-test-modes.png)

A continuación, puede configurar y ejecutar el modo de prueba como de costumbre. En [esta sección](../building-journeys/testing-the-journey.md) se describen los pasos detallados para probar un viaje.

Una vez ejecutada la prueba, el botón **[!UICONTROL Show logs]** le permite ver los resultados de la prueba según la opción de prueba seleccionada:

* **[!UICONTROL Single profile at a time]**:: los registros de prueba muestran la misma información que cuando se utiliza el modo de prueba unitario. Para obtener más información, consulte [esta sección](../building-journeys/testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**:: los registros de prueba le permiten rastrear la progresión de la exportación de segmentos desde Adobe Experience Platform, así como el progreso individual de todas las personas que entraron en el viaje.

   Tenga en cuenta que probar el viaje con hasta 100 perfiles a la vez no permite rastrear el progreso de los individuos en el viaje utilizando el flujo visual.

   ![](../assets/read-segment-log.png)

Una vez que las pruebas sean exitosas, puede publicar su viaje (consulte [Publicación del viaje](../building-journeys/publishing-the-journey.md)). Las personas que pertenezcan al segmento entrarán en el viaje en la fecha y hora especificadas en la sección de propiedades **[!UICONTROL Scheduler]** del viaje.

>[!NOTE]
>
>Al realizar una nueva versión de un viaje basado en segmentos que no sea recurrente (comenzando tan pronto como sea posible o &quot;una vez&quot;), todos los individuos que hayan entrado en el viaje anteriormente no volverán a introducir su nueva versión cuando la publique. Si desea permitir que vuelvan a entrar, debe realizar el duplicado del viaje.
