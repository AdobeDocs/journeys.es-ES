---
product: adobe campaign
title: Acerca de la creación de un recorrido
description: Como usuario empresarial, aprenda a combinar actividades de eventos, orquestación y acciones para construir un recorrido.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 12%

---

# Creación de un recorrido {#concept_gq5_sqt_52b}

Este paso lo realiza el **usuario empresarial**. Aquí es donde crea sus recorridos. Combine las distintas actividades de evento, orquestación y acción para crear sus escenarios de canal cruzado de varios pasos.

La interfaz de recorrido permite arrastrar y soltar fácilmente actividades de la paleta en el lienzo. También puede hacer doble clic en una actividad para agregarla al lienzo en el siguiente paso disponible. Cada actividad tiene una función y un lugar específicos en el proceso. Las actividades se secuencian. Cuando finaliza una actividad, el flujo continúa y procesa la siguiente actividad, etc.

Solo se permite un espacio de nombres por recorrido. Cuando se suelta el primer evento, los eventos con diferentes áreas de nombres aparecen atenuados. Si el primer evento no tiene un área de nombres, todos los eventos con un área de nombres se atenuarán. Consulte [esta página](../event/selecting-the-namespace.md). Además, los grupos de campos de Adobe Experience Platform aparecen atenuados si el recorrido tiene eventos sin área de nombres. Y, por último, si utiliza varios eventos en el mismo recorrido, deben utilizar el mismo espacio de nombres.

Al iniciar un nuevo recorrido, los elementos que no se pueden soltar en el lienzo como primer paso se ocultan. Esto se refiere a todas las acciones, la actividad de la condición, la espera y la reacción.

## Inicio rápido {#creating_journey}

Estos son los pasos principales para crear y publicar un recorrido.

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]**.

   Se muestra la lista de recorridos. Consulte [esta página](../building-journeys/using-the-journey-designer.md) para obtener más información sobre la interfaz.

   ![](../assets/journey30.png)

1. Haga clic en **[!UICONTROL Create]** para crear un nuevo recorrido.

   ![](../assets/journey31.png)

1. Edite las propiedades del recorrido en el panel de configuración que se muestra en el lado derecho. Consulte [esta página](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Para empezar, arrastre y suelte una actividad de evento de la paleta en el lienzo. También puede hacer doble clic en una actividad para agregarla al lienzo.

   ![](../assets/journey33.png)

1. Arrastre y suelte las demás actividades y configúrelas. Consulte las páginas [Actividades de evento](../building-journeys/event-activities.md), [Acerca de las actividades de organización](../building-journeys/about-orchestration-activities.md) y [Acerca de las actividades de acción](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. El recorrido se guarda automáticamente. Pruebe el recorrido y publíquelo. Consulte [prueba del recorrido](../building-journeys/testing-the-journey.md) y [Publicación del recorrido](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Finalización de un recorrido {#ending_a_journey}

Un recorrido puede finalizar para un individuo por dos razones:

* La persona llega a la última actividad de una ruta. Esta última actividad puede ser una actividad final u otra actividad. No hay obligación de finalizar una ruta con una actividad final. Consulte [esta página](../building-journeys/end-activity.md).
* La persona llega a una actividad de condición (o a una actividad de espera con una condición ) y no coincide con ninguna de las condiciones.

La persona puede volver a entrar en el recorrido si se permite la reentrada. Consulte [esta página](../building-journeys/changing-properties.md).

Un recorrido puede cerrarse por los siguientes motivos:

* El recorrido se cierra manualmente mediante la variable **[!UICONTROL Close to new entrances]** botón.
* Se alcanza la fecha de finalización del recorrido.

Cuando se cierra un recorrido (por cualquiera de los motivos anteriores), aparece el estado **[!UICONTROL Closed]**. El recorrido dejará de permitir la entrada al recorrido de nuevos individuos. Las personas que ya están en el recorrido terminarán normalmente el recorrido. Después del tiempo de espera global predeterminado de 30 días, el recorrido cambiará a la variable **Finalizado** estado. Consulte esta [sección](../building-journeys/changing-properties.md#entrance).

En caso de que necesite detener el progreso de todas las personas en el recorrido, puede detenerlo. Al detener el recorrido, se agotará el tiempo de espera de todas las personas del recorrido.

Para aprender a cerrar o detener un recorrido manualmente, consulte esta [sección](../building-journeys/terminating-a-journey.md).
