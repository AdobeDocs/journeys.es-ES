---
title: Actividad de condición
description: Información sobre actividades de condición
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 10%

---


# Actividad de condición{#section_e2n_pft_dgb}

Existen cuatro tipos de condiciones:

* [Condición de fuente de datos](#data_source_condition)
* [Condición de tiempo](#time_condition)
* [División de porcentaje](#percentage_split)
* [Condición de fecha](#date_condition)

![](../assets/journey49.png)

## Acerca de la actividad Condition {#about_condition}

Al utilizar varias condiciones en un viaje, puede definir etiquetas para cada una de ellas para identificarlas con mayor facilidad.

Haga clic **[!UICONTROL Add a path]** si desea definir varias condiciones. Para cada condición, se agrega una nueva ruta en el lienzo después de la actividad.

![](../assets/journey47.png)

Tenga en cuenta que el diseño de los viajes tiene un impacto funcional. Cuando se definen varias rutas después de una condición, solo se ejecutará la primera ruta elegible. Significa que puede variar la priorización de las rutas colocándolas encima o debajo de las demás.

Por ejemplo, tomemos el ejemplo de la condición de una primera ruta &quot;La persona es un VIP&quot; y la condición de una segunda ruta &quot;La persona es un hombre&quot;. Si una persona que cumple ambas condiciones (un hombre que es VIP) supera este paso, se elegirá la primera ruta aunque también sea elegible para la segunda, porque la primera es &quot;superior&quot;. Para cambiar esta prioridad, mueva las actividades en otro orden vertical.

![](../assets/journey48.png)

Puede crear otra ruta para audiencias que no cumplan las condiciones definidas marcando **[!UICONTROL Show path for other cases than the one(s) above]**. Tenga en cuenta que esta opción no está disponible en condiciones de división. Consulte [Porcentaje dividido](#percentage_split).

El modo simple permite realizar consultas sencillas basadas en una combinación de campos. Todos los campos disponibles se muestran en la parte izquierda de la pantalla. Arrastre y suelte los campos en la zona principal. Para combinar los distintos elementos, interactívelos entre sí para crear diferentes grupos o niveles de grupo. A continuación, puede seleccionar un operador lógico para combinar elementos en el mismo nivel:

* Y: una intersección de dos criterios. Sólo se tienen en cuenta los elementos que coinciden con todos los criterios.
* O: una unión de dos criterios. Se tienen en cuenta los elementos que coinciden con al menos uno de los dos criterios.

![](../assets/journey64.png)

Si utiliza el servicio [de segmentación de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) Adobe Experience Platform para crear sus segmentos, puede aprovecharlos en las condiciones de su viaje. Consulte [Uso de segmentos en condiciones](../segment/using-a-segment.md).


>[!NOTE]
>
>No puede realizar consultas en series temporales (por ejemplo, una lista de compras, clics anteriores en mensajes) con el editor simple. Para ello, deberá utilizar el editor avanzado. Consulte [esta página](../expression/expressionadvanced.md).

Cuando se produce un error en una acción o condición, se detiene el recorrido de un individuo. La única manera para continuar es marcar la casilla **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta sección](../building-journeys/using-the-journey-designer.md#paths).

## Condición de fuente de datos {#data_source_condition}

Esto le permite definir una condición en función de los campos de los orígenes de datos o los eventos colocados anteriormente en el viaje. Para obtener información sobre cómo utilizar el editor de expresiones, consulte [esta página](../expression/expressionadvanced.md). Con el editor de expresiones avanzado, puede configurar condiciones más avanzadas para manipular colecciones o utilizar orígenes de datos que requieran pasar parámetros. Consulte [esta página](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condición de tiempo{#time_condition}

Esto le permite realizar diferentes acciones según la hora del día y/o el día de la semana. Por ejemplo, puede decidir enviar mensajes SMS durante el día y mensajes de correo electrónico por la noche durante los días de semana.

>[!NOTE]
>
>El huso horario ya no es específico de una condición y ahora se define en el nivel de viaje en las propiedades del viaje. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## División de porcentaje {#percentage_split}

Esta opción le permite dividir aleatoriamente la audiencia para definir una acción diferente para cada grupo. Defina el número de divisiones y la partición para cada ruta. El cálculo de la división es estadístico, ya que el sistema no puede anticipar cuántas personas fluirán en esta actividad del viaje. Como resultado, la división tiene un margen de error muy bajo. Esta función se basa en un mecanismo aleatorio de Java (consulte esta [página](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Tenga en cuenta que no hay ningún botón para agregar una ruta en la condición de división de porcentaje. El número de rutas dependerá del número de divisiones. En condiciones de división, no puede agregar una ruta para otros casos, ya que no puede suceder. Las personas siempre van a uno de los caminos divididos.

![](../assets/journey52.png)

## Condición de fecha {#date_condition}

Esto le permite definir un flujo diferente en función de la fecha. Por ejemplo, si la persona entra en el paso durante el período de &quot;ventas&quot;, le enviará un mensaje específico. El resto del año, enviarás otro mensaje.

>[!NOTE]
>
>El huso horario ya no es específico de una condición y ahora se define en el nivel de viaje en las propiedades del viaje. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
