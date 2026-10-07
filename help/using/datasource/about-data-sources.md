---
product: adobe campaign
title: Acerca de las fuentes de datos
description: Obtenga información sobre cómo configurar una fuente de datos
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 83%
---
# Acerca de las fuentes de datos {#concept_s1s_dqt_52b}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._



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
