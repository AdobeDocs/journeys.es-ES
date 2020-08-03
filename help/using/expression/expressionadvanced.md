---
title: Acerca del editor de expresiones avanzadas
description: Aprenda a crear expresiones avanzadas
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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 3%

---


# Acerca del editor de expresiones avanzadas {#concept_uyj_trt_52b}

El editor de expresiones avanzado permite crear expresiones avanzadas en varias pantallas de la interfaz, por ejemplo, al definir una condición de fuente de datos.
También está disponible cada vez que necesite definir parámetros de acción que requieran manipulaciones de datos específicas. Puede aprovechar los datos procedentes de los eventos o la información adicional recuperada del origen de datos. En un viaje, la lista mostrada de los campos de evento es contextual y varía según los eventos agregados en el viaje.

El editor de expresiones avanzado oferta un conjunto de funciones y operadores integrados que le permiten manipular valores y definir una expresión que se ajuste específicamente a sus necesidades. El editor de expresiones avanzado también permite definir los valores del parámetro de origen de datos externo, manipular los campos y colecciones de mapas, como los eventos de experiencia.

![](../assets/journey65.png)

_Interfaz avanzada del editor de expresiones_

El editor de expresiones avanzado se puede utilizar para:

* crear condiciones [](../building-journeys/condition-activity.md#about_condition) avanzadas en fuentes de datos e información de evento
* definir actividades de [espera personalizadas](../building-journeys/wait-activity.md#custom)
* definir asignación de parámetros de acción

Cuando sea posible, puede cambiar entre los dos modos con el botón **[!UICONTROL Advanced mode]** / **[!UICONTROL Simple mode]** . El modo simple se describe [aquí](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>Las condiciones se pueden definir en el editor de expresiones simple o avanzado. Siempre devuelven un tipo booleano.
>
>Los parámetros de acción se pueden definir seleccionando campos o mediante el editor de expresiones avanzado. Devuelven un tipo de datos específico según su expresión.

## Accessing the advanced expression editor {#section_fdz_4nj_cjb}

Puede acceder al editor de expresiones avanzado de diferentes maneras:

* Al crear una condición de fuente de datos, puede acceder al editor avanzado haciendo clic en **[!UICONTROL Advanced mode]**.

   ![](../assets/journeyuc2_33.png)

* Al crear un temporizador personalizado, se mostrará directamente el editor avanzado.
* Cuando asigne un parámetro de acción, haga clic en **[!UICONTROL Advanced mode]**.

## Descubrimiento de la interfaz{#section_otq_tnj_cjb}

Esta pantalla le permite escribir manualmente su expresión.

![](../assets/journey70.png)

En la parte izquierda de la pantalla se muestran los campos y las funciones disponibles:

* **[!UICONTROL Events]**:: elija uno de los campos recibidos del evento de entrada. La lista mostrada de los campos de evento es contextual y varía según los eventos agregados en el viaje.
* **[!UICONTROL Data Sources]**:: elija entre la lista de campos disponibles en los grupos de campos de los orígenes de datos.
* **[!UICONTROL Functions]**:: elija entre una lista de funciones integradas que permitan realizar filtros complejos. Las funciones están organizadas por categorías.

![](../assets/journey65.png)

Un mecanismo de finalización automática muestra sugerencias contextuales.

![](../assets/journey68.png)

Un mecanismo de validación de sintaxis comprueba la integridad del código. Los errores se muestran en la parte superior del editor.

![](../assets/journey69.png)

**Necesidad de parámetros al crear condiciones con el editor de expresiones avanzado**

Si selecciona un campo de un origen de datos externo que requiere que se llame a un parámetro (consulte [](../datasource/external-data-sources.md). Por ejemplo, en una fuente de datos relacionada con el tiempo, un parámetro utilizado frecuentemente será &quot;city&quot; (ciudad). Como resultado, debe seleccionar dónde desea obtener este parámetro de ciudad. Las funciones también se pueden aplicar a parámetros para realizar cambios de formato o concatenaciones.

![](../assets/journeyuc2_19.png)

Para casos de uso más complejos, si desea incluir los parámetros del origen de datos en la expresión principal, puede definir sus valores con la palabra clave &quot;params&quot;. Consulte [esta página](../expression/field-references.md).
