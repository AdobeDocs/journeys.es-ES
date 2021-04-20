---
product: adobe campaign
solution: Journey Orchestration
title: Configuración de URL
description: Más información sobre la configuración de URL
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 9%

---


# Configuración de URL {#concept_gbg_1f1_2gb}

Al configurar una acción personalizada, debe definir los siguientes **[!UICONTROL URL Configuration]** parámetros:

![](../assets/journeyurlconfiguration.png)

1. Añada el **[!UICONTROL URL]** del servicio externo.

   >[!NOTE]
   >
   >Recomendamos encarecidamente utilizar HTTPS por motivos de seguridad. No permitimos el uso de direcciones de Adobe que no sean públicas ni de direcciones IP.

1. Seleccione la llamada **[!UICONTROL Method]**: puede ser **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. En la sección **[!UICONTROL Headers]** , haga clic en **[!UICONTROL Add a header field]** para definir un nuevo par clave/valor. Corresponden a los encabezados HTTP de la solicitud realizada al servicio externo. Para eliminar pares de clave/valor, coloque el cursor en el campo **[!UICONTROL Headers]** y haga clic en el icono **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** y  **[!UICONTROL Charset]** están configurados de forma predeterminada y no se pueden eliminar ni sobrescribir.

   >[!NOTE]
   >
   >Los encabezados se validan según las siguientes [reglas de análisis](https://tools.ietf.org/html/rfc7230#section-3.2.4).
