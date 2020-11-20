---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de la creación de un recorrido
description: Como usuario empresarial, aprenda a combinar actividades de eventos, orquestación y acciones para construir un recorrido.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---



# Creación de un recorrido {#concept_gq5_sqt_52b}

This step is performed by the **business user**. Aquí es donde crea sus viajes. Combine las distintas actividades de evento, orquestación y acción para crear sus escenarios de canal cruzado de varios pasos.

La interfaz de viaje permite arrastrar y soltar fácilmente actividades de la paleta en el lienzo. También puede hacer clic con el botón doble en una actividad para agregarla al lienzo en el siguiente paso disponible. Cada actividad tiene una función y un lugar específicos en el proceso. Las actividades se secuencian. Cuando finaliza una actividad, el flujo continúa y procesa la siguiente actividad, etc.

Sólo se permite una Área de nombres por viaje. Cuando sueltes el primer evento, los eventos con diferentes Áreas de nombres aparecerán atenuados. Si el primer evento no tiene una Área de nombres, entonces todos los eventos con una Área de nombres estarán atenuados. Consulte [esta página](../event/selecting-the-namespace.md). Además, los grupos de campo de Adobe Experience Platform aparecen atenuados si el viaje tiene eventos sin Área de nombres. Y finalmente, si uno usa varios eventos en el mismo viaje, ellos necesitan usar la misma Área de nombres.

## Quick start {#creating_journey}

Estos son los pasos principales para crear y publicar un viaje.

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]**.

   Se muestra la lista de los viajes. Refer to [this page](../building-journeys/using-the-journey-designer.md) for more information on the interface.

   ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

   ![](../assets/journey31.png)

1. Edite las propiedades del recorrido en el panel de configuración que se muestra en el lado derecho. Consulte [esta página](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Para inicio, arrastre y suelte una actividad de evento de la paleta en el lienzo. También puede hacer clic con el doble en una actividad para agregarla al lienzo.

   ![](../assets/journey33.png)

1. Arrastre y suelte las demás actividades y configúrelas. Consulte las actividades [de](../building-journeys/event-activities.md)Evento de páginas, [Acerca de las actividades](../building-journeys/about-orchestration-activities.md) de orquestación y [Acerca de las actividades](../building-journeys/about-action-activities.md)de acción.

   ![](../assets/journey34.png)

1. Su viaje se guarda automáticamente. Pruebe su viaje y publíquelo. Consulte [Prueba del viaje](../building-journeys/testing-the-journey.md) y [Publicación del viaje](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Finalización de un viaje {#ending_a_journey}

Existen dos maneras de terminar un viaje:

* La persona llega a la última actividad de un camino. Esta última actividad puede ser una actividad final u otra actividad. No existe la obligación de poner fin a una ruta con una actividad final. Consulte [esta página](../building-journeys/end-activity.md).
* La persona llega a una actividad de condición (o a una actividad de espera con una condición) y no cumple ninguna de las condiciones.

La persona puede volver a entrar en el viaje si se permite la reentrada. Consulte [esta página](../building-journeys/changing-properties.md).
