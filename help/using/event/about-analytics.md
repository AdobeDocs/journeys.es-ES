---
product: adobe campaign
title: Acerca de los datos Adobe Analytics
description: Aprenda a aprovechar los datos de Adobe Analytics
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
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
source-wordcount: '246'
ht-degree: 21%
---
# Aprovechamiento de los datos de Adobe Analytics{#analytics-data}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


>[!NOTE]
>
>Esta sección solo se aplica a los eventos basados en reglas y a los clientes que necesitan utilizar datos de Adobe Analytics.

Puede aprovechar todos los datos de evento de comportamiento de Adobe Analytics que ya está capturando y transmitiendo a la plataforma para almacenar en déclencheur los recorridos y automatizar las experiencias para los clientes.

Para que esto funcione, debe activar en Adobe Experience Platform el grupo de informes que desee aprovechar:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Sources]** y después **[!UICONTROL Add data]** en la sección Adobe Analytics. Se muestra la lista de grupos de informes de Adobe Analytics disponibles.

1. Elija el grupo de informes que desea habilitar, haga clic en **[!UICONTROL Next]** y luego en **[!UICONTROL Finish]**.

1. Comparta el ID de datos de origen con el punto de contacto del programa de Alpha.

Esto habilita el conector de origen de Analytics para ese grupo de informes. Cada vez que llegan los datos, se transforman en un evento de Experience y se envían a Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obtener más información sobre el conector de origen de Adobe Analytics, consulte [documentación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) y [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
