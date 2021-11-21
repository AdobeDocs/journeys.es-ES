---
product: adobe campaign
title: Configuración de URL
description: Más información sobre la configuración de URL
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# Configuración de URL {#concept_gbg_1f1_2gb}

Al configurar una acción personalizada, debe definir lo siguiente **[!UICONTROL URL Configuration]** parámetros:

![](../assets/journeyurlconfiguration.png)

1. En el **[!UICONTROL URL]** especifique la URL del servicio externo:

   * Si la dirección URL es estática, introduzca la dirección URL en este campo.

   * Si la dirección URL incluye una ruta dinámica, introduzca únicamente la parte estática de la dirección URL, es decir, el esquema, el host, el puerto y, opcionalmente, una parte estática de la ruta.

      Ejemplo: `https://xxx.yyy.com/somethingstatic/`

      Al agregar la acción personalizada a un recorrido, especificará la ruta dinámica de la dirección URL. [Más información](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Por motivos de seguridad, recomendamos encarecidamente que utilice el esquema HTTPS para la dirección URL. No permitimos el uso de direcciones de Adobe que no sean públicas ni de direcciones IP.
   >
   >Solo se permiten los puertos predeterminados al definir una acción personalizada: 80 para http y 443 para https.

1. Seleccione la llamada **[!UICONTROL Method]**: puede ser **[!UICONTROL POST]** o **[!UICONTROL PUT]**.
1. En el **[!UICONTROL Headers]** , defina los encabezados HTTP del mensaje de solicitud que se enviarán al servicio externo:
   1. Para añadir un campo de encabezado, haga clic en **[!UICONTROL Add a header field]**.
   1. Introduzca la clave del campo de encabezado.
   1. Para establecer un valor dinámico para el par clave-valor, seleccione **[!UICONTROL Variable]**. De lo contrario, seleccione **[!UICONTROL Constant]**.

      Por ejemplo, para una marca de tiempo, puede establecer un valor dinámico.

   1. Si ha seleccionado **[!UICONTROL Constant]** y, a continuación, introduzca el valor constante.

      Si ha seleccionado **[!UICONTROL Variable]**, especificará esta variable al agregar la acción personalizada a un recorrido. [Más información](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Para eliminar un campo de encabezado, elija el campo de encabezado y haga clic en el botón **[!UICONTROL Delete]** icono.
   La variable **[!UICONTROL Content-Type]** y **[!UICONTROL Charset]** los campos de encabezado se establecen de forma predeterminada. Estos campos no se pueden modificar ni eliminar.

   Después de agregar la acción personalizada a un recorrido, puede agregarle campos de encabezado si el recorrido está en estado de borrador. Si no desea que el recorrido se vea afectado por los cambios de configuración, duplique la acción personalizada y añada los campos del encabezado a la nueva acción personalizada.

   >[!NOTE]
   >
   >Los encabezados se validan según las reglas de análisis de campos. [Más información](https://tools.ietf.org/html/rfc7230#section-3.2.4).
