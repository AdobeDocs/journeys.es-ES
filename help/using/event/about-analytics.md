---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de los datos de Adobe Analytics
description: Aprenda a aprovechar los datos de Adobe Analytics
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Aprovechamiento de los datos de Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Esta sección solo se aplica a los eventos basados en reglas y a los clientes que necesiten utilizar datos de Adobe Analytics.

Puede aprovechar todos los datos de evento de comportamiento de Adobe Analytics que ya está capturando y transmitiendo a la plataforma para activar viajes y automatizar experiencias para sus clientes.

Para que esto funcione, debe activar, en Adobe Experience Platform, el grupo de informes que desea aprovechar:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Sources]** y luego **[!UICONTROL Add data]** en la sección Adobe Analytics. Se muestra la lista de los grupos de informes de Adobe Analytics disponibles.

1. Elija el grupo de informes que desee habilitar, haga clic en **[!UICONTROL Next]** y haga clic en **[!UICONTROL Finish]**.

1. Comparta el ID de datos de origen con el punto de contacto del programa alfa.

Esto habilita el conector de origen de Analytics para ese grupo de informes. Cada vez que entran los datos, se transforman en un evento de experiencias y se envían a Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obtener más información sobre el conector de origen de Adobe Analytics, consulte la [documentación](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) y [tutorial](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
