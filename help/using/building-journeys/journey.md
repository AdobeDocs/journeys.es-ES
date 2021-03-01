---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de la creación de un recorrido
description: Como usuario empresarial, aprenda a combinar actividades de eventos, orquestación y acciones para construir un recorrido.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---


# Crear un recorrido {#concept_gq5_sqt_52b}

Este paso lo realiza el **usuario del negocio**. Aquí es donde crea sus recorridos. Combine las distintas actividades de evento, orquestación y acción para crear sus escenarios de canal cruzado de varios pasos.

La interfaz de recorrido permite arrastrar y soltar fácilmente actividades de la paleta en el lienzo. También puede hacer clic con el botón doble en una actividad para agregarla al lienzo en el siguiente paso disponible. Cada actividad tiene una función y un lugar específicos en el proceso. Las actividades se secuencian. Cuando finaliza una actividad, el flujo continúa y procesa la siguiente actividad, etc.

Solo se permite una Área de nombres por recorrido. Cuando sueltes el primer evento, los eventos con diferentes Áreas de nombres aparecerán atenuados. Si el primer evento no tiene una Área de nombres, entonces todos los eventos con una Área de nombres estarán atenuados. Consulte [esta página](../event/selecting-the-namespace.md). Además, los grupos de campos de Adobe Experience Platform aparecen atenuados si el recorrido tiene eventos sin Área de nombres. Y finalmente, si se utilizan varios eventos en el mismo recorrido, necesitan usar la misma Área de nombres.

## Inicio rápido {#creating_journey}

Estos son los pasos principales para crear y publicar un recorrido.

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]**.

   Se muestra la lista de recorridos. Consulte [esta página](../building-journeys/using-the-journey-designer.md) para obtener más información sobre la interfaz.

   ![](../assets/journey30.png)

1. Haga clic en **[!UICONTROL Create]** para crear un nuevo recorrido.

   ![](../assets/journey31.png)

1. Edite las propiedades del recorrido en el panel de configuración que se muestra en el lado derecho. Consulte [esta página](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Para inicio, arrastre y suelte una actividad de evento de la paleta en el lienzo. También puede hacer clic con el doble en una actividad para agregarla al lienzo.

   ![](../assets/journey33.png)

1. Arrastre y suelte las demás actividades y configúrelas. Consulte las páginas [actividades de Evento](../building-journeys/event-activities.md), [Acerca de las actividades de orquestación](../building-journeys/about-orchestration-activities.md) y [Acerca de las actividades de acción](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. El recorrido se guarda automáticamente. Pruebe el recorrido y publíquelo. Consulte [prueba del recorrido](../building-journeys/testing-the-journey.md) y [Publicación del recorrido](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Finalización de un recorrido {#ending_a_journey}

Existen dos formas de poner fin a un recorrido:

* La persona llega a la última actividad de un camino. Esta última actividad puede ser una actividad final u otra actividad. No existe la obligación de poner fin a una ruta con una actividad final. Consulte [esta página](../building-journeys/end-activity.md).
* La persona llega a una actividad de condición (o a una actividad de espera con una condición) y no cumple ninguna de las condiciones.

La persona puede volver a entrar en el recorrido si se permite la reentrada. Consulte [esta página](../building-journeys/changing-properties.md).
