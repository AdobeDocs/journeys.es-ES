---
product: adobe campaign
title: Acerca de los informes de recorrido
description: Obtenga información sobre cómo crear informes de recorrido
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 1%

---

# Acerca de los informes de recorrido {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Los datos de envío y el componente Segmentos solo se rellenarán si tiene Adobe Campaign Standard.

Esta sección le muestra cómo acceder y utilizar los informes para medir la efectividad de sus recorridos.

## Interfaz de informes {#reporting-interface}

La barra de herramientas superior permite, por ejemplo, modificar, guardar o imprimir el informe.

![](../assets/dynamic_report_toolbar.png)

Utilice la pestaña **[!UICONTROL Project]** para:

* **[!UICONTROL Open]**: abre un informe o una plantilla creados anteriormente.
* **[!UICONTROL Save As]**: duplica las plantillas para poder modificarlas.
* **[!UICONTROL Refresh project]**: actualiza el informe en función de los nuevos datos y cambios realizados en los filtros.
* **[!UICONTROL Download CSV]**: exporta los informes a un archivo CSV.
* **[!UICONTROL Print]**: imprime el informe.

La pestaña **[!UICONTROL Edit]** le permite:

* **[!UICONTROL Undo]**: cancela la última acción del panel.
* **[!UICONTROL Redo]**: cancela la última  **[!UICONTROL Undo]** acción del panel.
* **[!UICONTROL Clear all]**: elimina todos los paneles del tablero.

La tabla **[!UICONTROL Insert]** permite personalizar los informes mediante la adición de gráficos y tablas al tablero:

* **[!UICONTROL New Blank Panel]**: agrega un nuevo panel en blanco al tablero.
* **[!UICONTROL New Freeform]**: agrega una nueva tabla improvisada al tablero.
* **[!UICONTROL New Line]**: agrega un nuevo gráfico de líneas al tablero.
* **[!UICONTROL New Bar]**: agrega un nuevo gráfico de barras al tablero.

Las pestañas de la izquierda permiten crear el informe y filtrar los datos según sea necesario.

![](../assets/dynamic_report_interface.png)

Estas pestañas le permiten acceder a los siguientes elementos:

* **[!UICONTROL Panels]**: agregue un panel en blanco o una forma libre al informe para filtrar los datos. Para obtener más información, consulte la sección [Añadir paneles](../reporting/creating-your-journey-reports.md#adding-panels)
* **[!UICONTROL Visualizations]**: arrastre y suelte una selección de elementos de visualización para proporcionar al informe una dimensión gráfica. Para obtener más información, consulte la sección [Añadir visualizaciones](../reporting/creating-your-journey-reports.md#adding-visualizations) .
* **[!UICONTROL Components]**: personalice los informes con diferentes dimensiones, métricas, segmentos y períodos de tiempo. Para obtener más información, consulte la sección [Adición de componentes](../reporting/creating-your-journey-reports.md#adding-components) .

## Plantilla de resumen del recorrido {#ootb-template}

Los informes se dividen en dos categorías: una plantilla predeterminada e informes personalizados.
La plantilla predeterminada, **[!UICONTROL Journey summary]**, le proporciona una vista clara de los datos de seguimiento más importantes.

![](../assets/dynamic_report_journey_8.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivos ajustes de visualización.

Los siguientes KPI están disponibles en la parte superior del informe:

* **[!UICONTROL Journey - Entered]**: número total de personas que llegaron al evento de entrada del recorrido.
* **[!UICONTROL Journey - Completion rate]**: número total de personas que llegaron al final del recorrido (o en caso de que una persona no coincida con ninguna condición) comparado con el número total de personas que ingresaron al recorrido.
* **[!UICONTROL Journey - Current]**: número total de personas actualmente en el recorrido.
* **[!UICONTROL Journey - Failed rate]**: número total de recorridos que no se ejecutaron correctamente comparados con el número de recorridos en ejecución.
* **[!UICONTROL Delivery - Messages sent]**: número total de mensajes enviados.
* **[!UICONTROL Delivery rate]**: número total de mensajes enviados correctamente comparados con los mensajes enviados.
* **[!UICONTROL Delivery - Bounce rate]**: número total de mensajes devueltos en comparación con los mensajes enviados.
* **[!UICONTROL Delivery - Unsubscribed rate]**: número total de bajas de suscripción por destinatario en comparación con los mensajes enviados.
* **[!UICONTROL Delivery - Open rate]**: número total de mensajes abiertos comparados con el número de mensajes enviados.
* **[!UICONTROL Delivery - Click rate]**: número total de clics en un envío comparado con el número de mensajes enviados.

La visualización del flujo de Recorrido le permite ver la ruta de los perfiles de destino paso a paso a través del recorrido. Esto solo está disponible cuando se segmenta un recorrido. Se genera automáticamente y no se puede modificar.

![](../assets/dynamic_report_journey_10.png)

La tabla **[!UICONTROL Journey summary]** contiene los datos disponibles para su recorrido, como:

* **[!UICONTROL Entered]**: número total de personas que llegaron al evento de entrada del recorrido.
* **[!UICONTROL Completion rate]**: número total de personas que alcanzaron el control de flujo final del recorrido en comparación con el número total de personas que ingresaron al recorrido.
* **[!UICONTROL Current]**: número total de personas actualmente en el recorrido.
* **[!UICONTROL Failed]**: número total de recorridos que no se ejecutaron correctamente.
* **[!UICONTROL Failed rate]**: número total de recorridos que no se ejecutaron correctamente comparados con el número de recorridos en ejecución.

La tabla **[!UICONTROL Top events]** muestra los eventos con mayor éxito y las **[!UICONTROL Top action]** acciones con más éxito de sus recorridos.

![](../assets/dynamic_report_journey_11.png)

La tabla **[!UICONTROL Delivery - Sending summary]** contiene los datos disponibles para los envíos de su recorrido, como:

* **[!UICONTROL Processed/sent]**: número total de mensajes enviados.
* **[!UICONTROL Delivered rate]**: número total de mensajes enviados correctamente comparados con los mensajes enviados.
* **[!UICONTROL Delivered]**: número de mensajes enviados correctamente, en relación con el número total de mensajes enviados.
* **[!UICONTROL Bounce + error rate]**: número total de mensajes devueltos en comparación con los mensajes enviados.
* **[!UICONTROL Bounces + errors]**: total de errores acumulados durante la entrega y el procesamiento automático de devoluciones en relación con la cantidad total de mensajes enviados.

La tabla **[!UICONTROL Delivery - Tracking summary]** contiene los datos disponibles para realizar un seguimiento del éxito de los envíos de sus recorridos, como:

* **[!UICONTROL Open Rate]**: porcentaje de mensajes abiertos.
* **[!UICONTROL Open]**: número de veces que se abrió un mensaje en una entrega.
* **[!UICONTROL Click trough rate]**: número total de clics en un envío comparado con el número de mensajes enviados.
* **[!UICONTROL Click]**: número de veces que se hizo clic en un contenido en una entrega.
* **[!UICONTROL Unsubscribe rate]**: porcentaje de bajas de suscripción por destinatario comparado con los mensajes enviados.
* **[!UICONTROL Unsubscribed]**: número total de bajas de suscripción por destinatario en comparación con los mensajes enviados.
