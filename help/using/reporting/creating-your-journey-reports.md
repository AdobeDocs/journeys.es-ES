---
title: Creación de informes de recorrido
description: Conozca cómo crear sus informes de viaje
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 5%

---


# Creación de informes de recorrido {#concept_rfj_wpt_52b}

## Acceso y creación de informes {#accessing-reports}

>[!NOTE]
>
>Después de eliminar un viaje, todos los informes asociados ya no estarán disponibles.

Esta sección le mostrará cómo crear o utilizar informes predeterminados. Combine paneles, componentes y visualizaciones para rastrear mejor el éxito de sus viajes.

Para acceder a los informes de viajes y al inicio de seguimiento del éxito de sus envíos:

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]**.

1. Seleccione el viaje sobre el que desee informar.

   Tenga en cuenta que también puede acceder a los informes haciendo clic en **Informe** mientras pasa el ratón por encima de un viaje en la lista de viajes.

   ![](../assets/dynamic_report_journey.png)

1. Haga clic en el **[!UICONTROL Report]** icono en la parte superior derecha de la pantalla.

   ![](../assets/dynamic_report_journey_2.png)

1. El informe **[!UICONTROL Journey summary]** predeterminado aparece en pantalla. Para acceder a los informes personalizados, haga clic en el **[!UICONTROL Close]** botón .

   ![](../assets/dynamic_report_journey_12.png)

1. Haga clic en para **[!UICONTROL Create new project]** crear el informe desde cero.

   ![](../assets/dynamic_report_journey_3.png)

1. En la **[!UICONTROL Panels]** ficha, arrastre y suelte tantos paneles o tablas improvisadas como sea necesario. Para obtener más información, consulte esta [sección](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. A continuación, puede filtrar los datos mediante inicios arrastrando y soltando dimensiones y métricas desde la **[!UICONTROL Components]** ficha hasta la tabla improvisada. Para obtener más información, consulte esta [sección](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Para obtener una vista más clara de los datos, puede agregar visualizaciones desde la **[!UICONTROL Visualizations]** ficha. Para obtener más información, consulte esta [sección](#adding-visualizations).

## Adición de paneles{#adding-panels}

### Añadir un panel en blanco {#adding-a-blank-panel}

Para inicio del informe, puede agregar un conjunto de paneles a un informe predeterminado o personalizado. Cada panel contiene diferentes conjuntos de datos y está compuesto de tablas y visualizaciones improvisadas.

Este panel le permite generar los informes según sea necesario. Puede agregar tantos paneles como desee en los informes para filtrar los datos con diferentes períodos de tiempo.

1. Haga clic en el icono **[!UICONTROL Panels]**. También puede agregar un panel haciendo clic en el **[!UICONTROL Insert tab]** y seleccionando **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el **[!UICONTROL Blank Panel]** panel.

   ![](../assets/dynamic_report_panel.png)

Ahora puede agregar una tabla improvisada al panel a los datos de objetivo de inicio.

### Añadir una tabla improvisada {#adding-a-freeform-table}

Las tablas improvisadas permiten crear una tabla para analizar los datos con las distintas métricas y dimensiones disponibles en la **[!UICONTROL Component]** tabla.

Se puede cambiar el tamaño de cada tabla y visualización y moverlas para personalizar mejor el informe.

1. Haga clic en el icono **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el **[!UICONTROL Freeform]** elemento en el panel.

   También puede agregar una tabla haciendo clic en la **[!UICONTROL Insert]** ficha y seleccionando **[!UICONTROL New Freeform]** o haciendo clic **[!UICONTROL Add a freeform table]** en un panel vacío.

   ![](../assets/dynamic_report_panel_2.png)

1. Arrastre y suelte los elementos de la **[!UICONTROL Components]** ficha en las columnas y filas para crear la tabla.

   ![](../assets/dynamic_report_freeform_3.png)

1. Haga clic en el **[!UICONTROL Settings]** icono para cambiar la forma en que se muestran los datos en las columnas.

   ![](../assets/dynamic_report_freeform_4.png)

   El **[!UICONTROL Column settings]** grupo está compuesto por:

   * **[!UICONTROL Number]**:: permite mostrar u ocultar los números de resumen en la columna.
   * **[!UICONTROL Percent]**:: permite mostrar u ocultar los porcentajes de la columna.
   * **[!UICONTROL Interpret zero as no value]**:: permite mostrar u ocultar cuando el valor es igual a cero.
   * **[!UICONTROL Background]**:: permite mostrar u ocultar la barra de progreso horizontal en las celdas.
   * **[!UICONTROL Include retries]**:: permite incluir reintentos en el resultado. Esto solo está disponible para **[!UICONTROL Sent]** y **[!UICONTROL Bounces + Errors]**.

1. Seleccione una o varias filas y haga clic en el **[!UICONTROL Visualize]** icono. Se agrega una visualización para reflejar las filas seleccionadas.

   ![](../assets/dynamic_report_freeform_5.png)

Ahora puede agregar tantos componentes como necesite y también agregar visualizaciones para proporcionar representaciones gráficas de los datos.

## Adición de componentes{#adding-components}

Los componentes ayudan a personalizar los informes con diferentes dimensiones, métricas y períodos de tiempo.

1. Haga clic en la **[!UICONTROL Components]** ficha para acceder a la lista de componentes.

   ![](../assets/dynamic_report_components.png)

1. Cada categoría presentada en la **[!UICONTROL Components]** ficha muestra los cinco elementos más utilizados, haga clic en el nombre de una categoría para acceder a su lista completa de componentes.

   La tabla de componentes se divide en tres categorías:

   * **[!UICONTROL Dimensions]**:: Obtenga detalles del registro de envíos, como el explorador o dominio del destinatario, o el éxito de un envío.
   * **[!UICONTROL Metrics]**:: Obtenga detalles sobre el estado de un mensaje. Por ejemplo, si se entregó un mensaje y el usuario lo abrió.
   * **[!UICONTROL Time]**:: Establezca un período de tiempo para la tabla.

1. Arrastre y suelte los componentes de un panel para filtrar los datos en inicio.

Puede arrastrar y soltar tantos componentes como sea necesario y compararlos entre sí.

## Adición de visualizaciones{#adding-visualizations}

La **[!UICONTROL Visualizations]** ficha permite arrastrar y soltar elementos de visualización, como área, anillo y gráfico. Las visualizaciones le proporcionan representaciones gráficas de sus datos.

1. En la **[!UICONTROL Visualizations]** ficha, arrastre y suelte un elemento de visualización en un panel.

   ![](../assets/dynamic_report_visualization_1.png)

1. Después de agregar una visualización al panel, los informes detectarán automáticamente los datos en la tabla improvisada. Seleccione la configuración de la visualización.
1. Si tiene más de una tabla improvisada, elija el origen de datos disponible para agregar el gráfico en la **[!UICONTROL Data Source Settings]** ventana. Esta ventana también está disponible haciendo clic en el punto de color al lado del título de visualización.

   ![](../assets/dynamic_report_visualization_2.png)

1. Haga clic en el botón **[!UICONTROL Visualization]** de configuración para cambiar directamente el tipo de gráfico o lo que se muestra en él, como:

   * **[!UICONTROL Percentages]**:: Muestra los valores en porcentaje.
   * **[!UICONTROL Anchor Y Axis at Zero]**:: Fuerza el eje y a cero incluso si los valores están por encima de cero.
   * **[!UICONTROL Legend visible]**:: Permite ocultar la leyenda.
   * **[!UICONTROL Normalization]**:: Obliga a que los valores coincidan.
   * **[!UICONTROL Display Dual Axis]**:: Añade otro eje al gráfico.
   * **[!UICONTROL Limit Max Items]**:: Limita el número de gráficos mostrados.
   * **[!UICONTROL Threshold]**:: Permite establecer un umbral en el gráfico. Aparece como una línea de puntos negra.

   ![](../assets/dynamic_report_visualization_3.png)

Esta visualización permite tener una vista más clara de los datos en los informes.