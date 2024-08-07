---
product: adobe campaign
title: Acerca de las fuentes de datos
description: Obtenga información sobre cómo configurar una fuente de datos
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 82%

---

# Acerca de las fuentes de datos {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Acerca de las fuentes de datos"
>abstract="La configuración de la fuente de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los recorridos."

La configuración de la fuente de datos permite definir una conexión con un sistema para recuperar información adicional que se utilizará en los recorridos, para: 


* [definición de condición](../building-journeys/condition-activity.md)
* datos de parámetros y personalización en [acciones](../action/action.md)
* [definición de espera personalizada](../building-journeys/wait-activity.md#custom)
* [definición de zona horaria](../building-journeys/timezone-management.md)

Esta configuración no es necesaria si los recorridos solo aprovechan los datos locales procedentes de una carga útil de evento. Por ejemplo, si el recorrido está compuesto por un evento seguido de una actividad de correo electrónico que solo utiliza datos del evento, no es necesario configurar ninguna fuente de datos.

Existen dos tipos de fuentes de datos:

* Fuente de datos preconfigurada de Adobe Experience Platform que define la conexión al servicio perfil de cliente en tiempo real. Constituye una fuente de datos integrada. Consulte [esta página](../datasource/adobe-experience-platform-data-source.md).
* Las fuentes de datos externas que permiten definir una conexión con sistemas externos. Estos son los que puede crear. Consulte [esta página](../datasource/external-data-sources.md).

Para cada fuente de datos, se define la información que se recuperará mediante grupos de campos. Los grupos de campos son conjuntos de campos que se pueden recuperar desde una fuente de datos. Consulte [esta página](../datasource/field-groups.md).

Para obtener más información sobre cómo configurar una fuente de datos de Adobe Experience Platform y una fuente de datos externa, y cómo buscar y usar los datos en un recorrido, vea este [vídeo tutorial](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Estos son los pasos principales de la configuración de la fuente de datos:

>[!NOTE]
>
>La configuración de la fuente de datos siempre la realiza un **usuario técnico**.

1. En el panel de menú, seleccione **[!UICONTROL Admin]**. En la sección **[!UICONTROL Data sources]**, haga clic en **[!UICONTROL Manage]**.

   Se muestra la lista de las fuentes de datos. Consulte [esta página](../about/user-interface.md) para obtener más información sobre la interfaz.

   ![](../assets/journey18.png)

1. A continuación, puede agregar grupos de campos al origen de datos integrado (vea [esta página](../datasource/adobe-experience-platform-data-source.md)) o crear un nuevo origen de datos externo (vea [esta página](../datasource/external-data-sources.md)) y grupos de campos asociados (vea [esta página](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Haga clic en **[!UICONTROL Save]**.

   La fuente de datos está ahora configurada y lista para utilizarse en sus recorridos.
