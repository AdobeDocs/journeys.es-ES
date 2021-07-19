---
product: adobe campaign
title: Configuración de URL
description: Más información sobre la configuración de URL
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 14%

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
