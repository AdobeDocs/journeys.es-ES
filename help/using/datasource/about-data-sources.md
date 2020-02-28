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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---


# Acerca de las fuentes de datos {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Acerca de las fuentes de datos&quot;
>abstract=&quot;La configuración del origen de datos siempre la realiza un usuario técnico. La configuración del origen de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los viajes, para: definición de condición, parámetro y datos de personalización en acciones, definición de espera personalizada, definición de zona horaria personalizada.&quot;

La configuración del origen de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los viajes, para:

* [definición de condición](../building-journeys/condition-activity.md)
* datos de parámetros y personalización en [acciones](../action/action.md)
* [definición de espera personalizada](../building-journeys/wait-activity.md#custom)
* [definición de zona horaria personalizada](../building-journeys/timezone-management.md)

Esta configuración no es necesaria si los viajes solo aprovechan los datos locales procedentes de una carga útil de evento. Por ejemplo, si el viaje está compuesto por un evento seguido de una actividad de correo electrónico que solo utiliza datos del evento, no es necesario configurar un origen de datos.

Existen dos tipos de fuentes de datos:

* Origen de datos preconfigurado de la plataforma de experiencia que define la conexión con el servicio de perfiles de cliente en tiempo real. Constituye una fuente de datos integrada. Consulte [](../datasource/adobe-experience-platform-data-source.md).
* Las fuentes de datos externas que permiten definir una conexión con sistemas externos. Estos son los que puede crear. Consulte [](../datasource/external-data-sources.md).

Para cada origen de datos, se define la información que se recuperará mediante grupos de campos. Los grupos de campos son conjuntos de campos que se pueden recuperar desde un origen de datos. Consulte [](../datasource/field-groups.md).

Para obtener más información sobre cómo configurar una fuente de datos de la plataforma de experiencia y una fuente de datos externa y cómo buscar y utilizar datos en un viaje, vea este [tutorial en vídeo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Estos son los pasos principales de la configuración del origen de datos:

>[!NOTE]
>
>La configuración del origen de datos siempre la realiza un usuario **** técnico.

1. En el menú superior, haga clic en la **[!UICONTROL Data Sources]** ficha.

   Se muestra la lista de fuentes de datos. Consulte [](../about/user-interface.md) para obtener más información sobre la interfaz.

   ![](../assets/journey18.png)

1. A continuación, puede agregar grupos de campos al origen de datos integrado (consulte [](../datasource/adobe-experience-platform-data-source.md)) o crear un nuevo origen de datos externo (consulte [](../datasource/external-data-sources.md)) y grupos de campos asociados (consulte [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Haga clic **[!UICONTROL Save]**.

   La fuente de datos está ahora configurada y lista para utilizarse en sus viajes.
