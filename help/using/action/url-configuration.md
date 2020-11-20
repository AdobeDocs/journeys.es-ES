---
product: adobe campaign
solution: Journey Orchestration
title: Configuración de URL
description: Más información sobre la configuración de URL
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# Configuración de URL {#concept_gbg_1f1_2gb}

Al configurar una acción personalizada, debe definir los **[!UICONTROL URL Configuration]** parámetros siguientes:

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >Recomendamos encarecidamente utilizar HTTPS por motivos de seguridad. No permitimos el uso de direcciones de Adobe que no sean públicas ni de direcciones IP.

1. Seleccione la llamada **[!UICONTROL Method]**: puede ser **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. En la **[!UICONTROL Headers]** sección, haga clic en **[!UICONTROL Add a header field]** para definir un nuevo par clave/valor. Corresponden a los encabezados HTTP de la solicitud realizada al servicio externo. Para eliminar pares de clave/valor, coloque el cursor en el **[!UICONTROL Headers]** campo y haga clic en el **[!UICONTROL Delete]** icono .

   **[!UICONTROL Content-Type]** y **[!UICONTROL Charset]** se establecen de forma predeterminada y no se pueden eliminar ni anular.

   >[!NOTE]
   >
   >Los encabezados se validan según las siguientes reglas [de](https://tools.ietf.org/html/rfc7230#section-3.2.4)análisis.
