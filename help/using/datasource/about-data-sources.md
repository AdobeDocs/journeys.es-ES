---
title: Acerca de las fuentes de datos
description: 'Obtenga información sobre cómo configurar una fuente de datos '
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 74%

---


# Acerca de las fuentes de datos {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Acerca de las fuentes de datos"
>abstract="La configuración de la fuente de datos siempre la realiza un usuario técnico. La configuración del origen de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los viajes, para: definición de condición, parámetro y datos de personalización en acciones, definición de espera personalizada, definición de zona horaria."

La configuración de la fuente de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los viajes, para:

* [definición de condición](../building-journeys/condition-activity.md)
* datos de parámetros y personalización en [acciones](../action/action.md)
* [definición de espera personalizada](../building-journeys/wait-activity.md#custom)
* [definición de zona horaria](../building-journeys/timezone-management.md)

Esta configuración no es necesaria si los recorridos solo aprovechan los datos locales procedentes de una carga útil de evento. Por ejemplo, si el recorrido está compuesto por un evento seguido de una actividad de correo electrónico que solo utiliza datos del evento, no es necesario configurar ninguna fuente de datos.

Existen dos tipos de fuentes de datos:

* Origen de datos de Adobe Experience Platform preconfigurado que define la conexión al servicio de Perfil del cliente en tiempo real. Constituye una fuente de datos integrada. Consulte [](../datasource/adobe-experience-platform-data-source.md).
* Las fuentes de datos externas que permiten definir una conexión con sistemas externos. Estos son los que puede crear. Consulte [](../datasource/external-data-sources.md).

Para cada fuente de datos, se define la información que se recuperará mediante grupos de campos. Los grupos de campos son conjuntos de campos que se pueden recuperar desde una fuente de datos. Consulte [](../datasource/field-groups.md).

For more information on how to configure an Adobe Experience Platform Data Source and an external data source and how to find and use data in a journey, watch this [tutorial video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Estos son los pasos principales de la configuración de la fuente de datos:

>[!NOTE]
>
>La configuración de la fuente de datos siempre la realiza un **usuario técnico**.

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Data Sources]**.

   Se muestra la lista de las fuentes de datos. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

   ![](../assets/journey18.png)

1. A continuación, puede agregar grupos de campos a la fuente de datos integrada (consulte [](../datasource/adobe-experience-platform-data-source.md)) o crear una nueva fuente de datos externa (consulte [](../datasource/external-data-sources.md)) y grupos de campos asociados (consulte [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Haga clic **[!UICONTROL Save]**.

   La fuente de datos está ahora configurada y lista para utilizarse en sus recorridos.
