---
product: adobe campaign
title: Creación de informes de recorrido
description: Obtenga información sobre cómo crear informes de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 5%

---

# Creación de informes de recorrido {#concept_rfj_wpt_52b}

## Acceso y creación de informes {#accessing-reports}

>[!NOTE]
>
>Después de eliminar un recorrido, todos los informes asociados ya no estarán disponibles.

Esta sección le muestra cómo crear o utilizar informes predeterminados. Combine paneles, componentes y visualizaciones para rastrear mejor el éxito de sus recorridos.

Para acceder a los informes de sus recorridos y empezar a rastrear el éxito de sus envíos:

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]**.

1. Seleccione el recorrido sobre el que desee informar.

   Tenga en cuenta que también puede acceder a sus informes haciendo clic en **Informe** mientras pasa el ratón por encima de un recorrido en la lista de recorridos.

   ![](../assets/dynamic_report_journey.png)

1. Haga clic en el icono **[!UICONTROL Report]** en la parte superior derecha de la pantalla.

   ![](../assets/dynamic_report_journey_2.png)

1. El informe predeterminado **[!UICONTROL Journey summary]** aparece en pantalla. Para acceder a los informes personalizados, haga clic en el botón **[!UICONTROL Close]** .

   ![](../assets/dynamic_report_journey_12.png)

1. Haga clic en **[!UICONTROL Create new project]** para crear el informe desde cero.

   ![](../assets/dynamic_report_journey_3.png)

1. En la ficha **[!UICONTROL Panels]**, arrastre y suelte tantos paneles o tablas de forma libre como sea necesario. Para obtener más información, consulte esta [sección](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. A continuación, puede empezar a filtrar los datos arrastrando y soltando dimensiones y métricas desde la pestaña **[!UICONTROL Components]** hasta la tabla de forma libre. Para obtener más información, consulte esta [sección](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Para obtener una vista más clara de los datos, puede agregar visualizaciones desde la pestaña **[!UICONTROL Visualizations]**. Para obtener más información, consulte esta [sección](#adding-visualizations).

## Adición de paneles{#adding-panels}

### Adición de un panel en blanco {#adding-a-blank-panel}

Para iniciar el informe, puede agregar un conjunto de paneles a un informe predeterminado o personalizado. Cada panel contiene diferentes conjuntos de datos y está compuesto por tablas improvisadas y visualizaciones.

Este panel le permite crear los informes según sea necesario. Puede agregar tantos paneles como desee en los informes para filtrar los datos con diferentes períodos de tiempo.

1. Haga clic en el icono **[!UICONTROL Panels]**. También puede agregar un panel haciendo clic en **[!UICONTROL Insert tab]** y seleccionando **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el **[!UICONTROL Blank Panel]** en el tablero.

   ![](../assets/dynamic_report_panel.png)

Ahora puede agregar una tabla improvisada al panel para comenzar a segmentar los datos.

### Adición de una tabla improvisada {#adding-a-freeform-table}

Las tablas improvisadas le permiten crear una tabla para analizar sus datos con las diferentes métricas y dimensiones disponibles en la tabla **[!UICONTROL Component]**.

Cada tabla y visualización se puede cambiar de tamaño y se puede mover para personalizar mejor el informe.

1. Haga clic en el icono **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el elemento **[!UICONTROL Freeform]** en el tablero.

   También puede agregar una tabla haciendo clic en la pestaña **[!UICONTROL Insert]** y seleccionando **[!UICONTROL New Freeform]** o haciendo clic en **[!UICONTROL Add a freeform table]** en un panel vacío.

   ![](../assets/dynamic_report_panel_2.png)

1. Arrastre y suelte los elementos de la ficha **[!UICONTROL Components]** en las columnas y filas para crear la tabla.

   ![](../assets/dynamic_report_freeform_3.png)

1. Haga clic en el icono **[!UICONTROL Settings]** para cambiar cómo se muestran los datos en las columnas.

   ![](../assets/dynamic_report_freeform_4.png)

   El **[!UICONTROL Column settings]** está compuesto por:

   * **[!UICONTROL Number]**: permite mostrar u ocultar los números de resumen en la columna .
   * **[!UICONTROL Percent]**: permite mostrar u ocultar porcentajes en la columna .
   * **[!UICONTROL Interpret zero as no value]**: permite mostrar u ocultar cuando el valor es igual a cero.
   * **[!UICONTROL Background]**: permite mostrar u ocultar la barra de progreso horizontal en las celdas.
   * **[!UICONTROL Include retries]**: permite incluir reintentos en el resultado. Esto solo está disponible para **[!UICONTROL Sent]** y **[!UICONTROL Bounces + Errors]**.

1. Seleccione una o varias filas y haga clic en el icono **[!UICONTROL Visualize]**. Se añade una visualización para reflejar las filas seleccionadas.

   ![](../assets/dynamic_report_freeform_5.png)

Ahora puede agregar tantos componentes como necesite y también agregar visualizaciones para proporcionar representaciones gráficas de sus datos.

## Adición de componentes{#adding-components}

Los componentes ayudan a personalizar los informes con diferentes dimensiones, métricas y períodos de tiempo.

1. Haga clic en la pestaña **[!UICONTROL Components]** para acceder a la lista de componentes.

   ![](../assets/dynamic_report_components.png)

1. Cada categoría presentada en la pestaña **[!UICONTROL Components]** muestra los cinco elementos más utilizados, haga clic en el nombre de una categoría para acceder a su lista completa de componentes.

   La tabla de componentes se divide en tres categorías:

   * **[!UICONTROL Dimensions]**: Obtenga detalles del registro de envíos, como el navegador o dominio del destinatario, o el éxito de una entrega.
   * **[!UICONTROL Metrics]**: Obtenga detalles sobre el estado de un mensaje. Por ejemplo, si se entregó un mensaje y el usuario lo abrió.
   * **[!UICONTROL Time]**: Establezca un período de tiempo para la tabla.

1. Arrastre y suelte los componentes en un panel para comenzar a filtrar los datos.

Puede arrastrar y soltar tantos componentes como sea necesario y compararlos entre sí.

## Adición de visualizaciones{#adding-visualizations}

La pestaña **[!UICONTROL Visualizations]** permite arrastrar y soltar elementos de visualización, como área, anillo y gráfico. Las visualizaciones le proporcionan representaciones gráficas de sus datos.

1. En la ficha **[!UICONTROL Visualizations]** , arrastre y suelte un elemento de visualización en un panel.

   ![](../assets/dynamic_report_visualization_1.png)

1. Después de agregar una visualización al panel, los informes detectarán automáticamente los datos en la tabla improvisada. Seleccione la configuración de la visualización.
1. Si tiene más de una tabla improvisada, elija el origen de datos disponible para agregar en el gráfico en la ventana **[!UICONTROL Data Source Settings]**. Esta ventana también está disponible haciendo clic en el punto de color al lado del título de visualización.

   ![](../assets/dynamic_report_visualization_2.png)

1. Haga clic en el botón de configuración **[!UICONTROL Visualization]** para cambiar directamente el tipo de gráfico o lo que se muestra en él, como:

   * **[!UICONTROL Percentages]**: Muestra los valores en porcentaje.
   * **[!UICONTROL Anchor Y Axis at Zero]**: Fuerza el eje y a cero incluso si los valores están por encima de cero.
   * **[!UICONTROL Legend visible]**: Permite ocultar la leyenda.
   * **[!UICONTROL Normalization]**: Fuerza que los valores coincidan.
   * **[!UICONTROL Display Dual Axis]**: Agrega otro eje al gráfico.
   * **[!UICONTROL Limit Max Items]**: Limita el número de gráficos mostrados.
   * **[!UICONTROL Threshold]**: Permite establecer un umbral en el gráfico. Aparece como una línea punteada negra.

   ![](../assets/dynamic_report_visualization_3.png)

Esta visualización le permite tener una vista más clara de los datos en los informes.
