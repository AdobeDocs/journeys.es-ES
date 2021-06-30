---
product: adobe campaign
title: Actividad de condición
description: Obtenga información sobre las actividades de condición
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 78c758c75825c0f85788190c4526fa5c743c6673
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---

# Actividad de condición{#section_e2n_pft_dgb}

Hay cuatro tipos de condiciones disponibles:

* [Condición de fuente de datos](#data_source_condition)
* [Condición horaria](#time_condition)
* [División de porcentaje](#percentage_split)
* [Condición de fecha](#date_condition)

![](../assets/journey49.png)

## Acerca de la actividad Condition {#about_condition}

Cuando se utilizan varias condiciones en un recorrido, se pueden definir etiquetas para cada una de ellas a fin de identificarlas con mayor facilidad.

Haga clic en **[!UICONTROL Add a path]** si desea definir varias condiciones. Para cada condición, se agrega una nueva ruta en el lienzo después de la actividad .

![](../assets/journey47.png)

Tenga en cuenta que el diseño de los recorridos tiene un impacto funcional. Cuando se definen varias rutas después de una condición, solo se ejecuta la primera ruta elegible. Significa que puede variar la priorización de las rutas colocándolas encima o debajo de las otras.

Por ejemplo, tomemos el ejemplo de la condición de una primera ruta &quot;La persona es un VIP&quot; y la condición de una segunda ruta &quot;La persona es un hombre&quot;. Si una persona que cumple ambas condiciones (un hombre que es VIP) supera este paso, la primera ruta se elegirá incluso si también es elegible para la segunda, ya que la primera ruta es &quot;superior&quot;. Para cambiar esta prioridad, mueva las actividades en otro orden vertical.

![](../assets/journey48.png)

Puede crear otra ruta para las audiencias que no cumplan los requisitos de las condiciones definidas marcando **[!UICONTROL Show path for other cases than the one(s) above]**. Tenga en cuenta que esta opción no está disponible en condiciones de división. Consulte [División porcentual](#percentage_split).

El modo simple permite realizar consultas simples basadas en una combinación de campos. Todos los campos disponibles se muestran en la parte izquierda de la pantalla. Arrastre y suelte los campos en la zona principal. Para combinar los distintos elementos, conéctelos entre sí para crear diferentes grupos o niveles de grupo. A continuación, puede seleccionar un operador lógico para combinar elementos en el mismo nivel:

* Y: una intersección de dos criterios. Solo se tienen en cuenta los elementos que coinciden con todos los criterios.
* O: una unión de dos criterios. Se tienen en cuenta los elementos que coinciden con al menos uno de los dos criterios.

![](../assets/journey64.png)

Si utiliza el [Servicio de segmentación de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) para crear sus segmentos, puede aprovecharlos en las condiciones de recorrido. Consulte [Uso de segmentos en condiciones](../segment/using-a-segment.md).


>[!NOTE]
>
>No puede realizar consultas en series temporales (por ejemplo, una lista de compras o clics anteriores en mensajes) con el editor simple. Para ello, debe utilizar el editor avanzado. Consulte [esta página](../expression/expressionadvanced.md).

Cuando se produce un error en una acción o condición, se detiene el recorrido de un individuo. La única manera para continuar es marcar la casilla **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta sección](../building-journeys/using-the-journey-designer.md#paths).

## Condición de fuente de datos {#data_source_condition}

Esto le permite definir una condición basada en los campos de las fuentes de datos o en los eventos colocados previamente en el recorrido. Para aprender a utilizar el editor de expresiones, consulte [esta página](../expression/expressionadvanced.md). Con el editor de expresiones avanzadas, puede configurar condiciones más avanzadas para manipular colecciones o utilizar fuentes de datos que requieran el paso de parámetros. Consulte [esta página](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condición horaria{#time_condition}

Esto le permite realizar diferentes acciones según la hora del día o el día de la semana. Por ejemplo, puede decidir enviar mensajes SMS durante el día y correos electrónicos durante la noche durante la semana.

>[!NOTE]
>
>La zona horaria ya no es específica de una condición y ahora se define a nivel de recorrido en las propiedades de recorrido. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## División de porcentaje {#percentage_split}

Esta opción le permite dividir aleatoriamente la audiencia para definir una acción diferente para cada grupo. Defina el número de divisiones y la repartición para cada ruta. El cálculo de la división es estadístico, ya que el sistema no puede anticipar cuántas personas fluirán en esta actividad del recorrido. Como resultado, la división tiene un margen de error muy bajo. Esta función se basa en un mecanismo aleatorio de Java (consulte esta [página](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

En el modo de prueba, al alcanzar una división, siempre se elige la rama superior. Puede reorganizar la posición de las ramas divididas si desea que la prueba elija una ruta diferente. Consulte [esta página](../building-journeys/testing-the-journey.md)

>[!NOTE]
>
>Tenga en cuenta que no hay ningún botón para agregar una ruta en la condición de división porcentual. El número de rutas dependerá del número de divisiones. En condiciones divididas, no se puede añadir una ruta para otros casos, ya que no puede suceder. Las personas siempre irán a una de las rutas divididas.

![](../assets/journey52.png)

## Condición de fecha {#date_condition}

Esto permite definir un flujo diferente en función de la fecha. Por ejemplo, si la persona introduce el paso durante el periodo de &quot;ventas&quot;, le envía un mensaje específico. El resto del año, usted enviará otro mensaje.

>[!NOTE]
>
>La zona horaria ya no es específica de una condición y ahora se define a nivel de recorrido en las propiedades de recorrido. Consulte [esta página](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
