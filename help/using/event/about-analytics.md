---
product: adobe campaign
title: Acerca de los datos de Adobe Analytics
description: Aprenda a aprovechar los datos de Adobe Analytics
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Aprovechamiento de los datos de Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Esta sección solo se aplica para eventos basados en reglas y clientes que necesitan utilizar datos de Adobe Analytics.

Puede aprovechar todos los datos de evento de comportamiento de Adobe Analytics que ya está capturando y transmitiendo a la plataforma para almacenar en déclencheur los recorridos y automatizar las experiencias para sus clientes.

Para que esto funcione, debe activar en Adobe Experience Platform el grupo de informes que desea aprovechar:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Sources]** y luego **[!UICONTROL Add data]** en la sección Adobe Analytics . Se muestra la lista de grupos de informes de Adobe Analytics disponibles.

1. Elija el grupo de informes que desea habilitar, haga clic en **[!UICONTROL Next]** y haga clic en **[!UICONTROL Finish]**.

1. Comparta el ID de datos de origen con el punto de contacto del programa Alpha.

Esto habilita el conector de origen de Analytics para ese grupo de informes. Cada vez que entran los datos, estos se transforman en un evento de Experience y se envían a Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obtener más información sobre el conector de origen de Adobe Analytics, consulte la [documentación](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) y el [tutorial](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
