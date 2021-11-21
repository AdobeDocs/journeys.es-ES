---
product: adobe campaign
title: Configuración de las fuentes de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso avanzado de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# Configuración de las fuentes de datos {#concept_vml_hdy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También tenemos que comprobar si la persona es un miembro socio y no ha sido contactada en las últimas 24 horas. Esta información se almacena en la base de datos Perfil del cliente en tiempo real. La variable **usuario técnico** debe configurar la fuente de datos de Adobe Experience Platform para recuperar esos campos.

Para obtener información adicional sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el panel de menú, seleccione **[!UICONTROL Admin]**. En el **[!UICONTROL Data sources]** , haga clic en **[!UICONTROL Manage]**.
1. Seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. En los campos de grupo preconfigurados, compruebe que los siguientes campos estén seleccionados:

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un **[!UICONTROL Profiles]** esquema y añadir **Miembro socio** para nuestra condición. La variable **Miembro socio** El campo es un campo personalizado y se agregó en XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un **[!UICONTROL ExperienceEvent]** y seleccione los campos necesarios para nuestra condición en el número de mensajes enviados en un periodo determinado: _timestamp_ para la fecha y _directMarketing > envía > valor_ para el número de mensajes enviados.

   ![](../assets/journeyuc2_7.png)

1. Haga clic en **[!UICONTROL Save]**.

También tenemos que comprobar si la persona tiene una reserva en el sistema de reservas de hotel. La variable **usuario técnico** debe configurar una segunda fuente de datos para recuperar este campo.

1. En la lista de fuentes de datos, haga clic en **[!UICONTROL Add]** para agregar una nueva fuente de datos externa para definir la conexión con su sistema de reservas de hotel.

   ![](../assets/journeyuc2_9.png)

1. Introduzca un nombre para la fuente de datos y la URL del servicio externo, por ejemplo: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Recomendamos encarecidamente utilizar HTTPS por motivos de seguridad.

1. Configure la autenticación según la configuración del servicio externo: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. En nuestro ejemplo, elegimos &quot;Básico&quot; para el tipo y especificamos el nombre de usuario y la contraseña para la llamada de API.

   ![](../assets/journeyuc2_10.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]** para definir la información que se va a recuperar y los parámetros de API. Para nuestro ejemplo, solo hay un parámetro (el id), por lo que necesitamos crear un grupo de campos con la siguiente información:

   * **[!UICONTROL Method]**: seleccione el método POST o GET. En nuestro caso, seleccionamos el método GET.
   * **[!UICONTROL Response Payload]**: haga clic dentro de **[!UICONTROL Payload]** y pegue un ejemplo de la carga útil. Compruebe que los tipos de campo son correctos. Cada vez que se llama a la API, el sistema recupera todos los campos incluidos en el ejemplo de carga útil. En nuestro ejemplo, la carga útil solo contiene el estado de reserva:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: introduzca el parámetro correspondiente a la clave utilizada para identificar a cada cliente, &quot;id&quot; en nuestro ejemplo. El valor de este parámetro se define en el recorrido .

   ![](../assets/journeyuc2_11.png)

1. Haga clic en **[!UICONTROL Save]**.

   Las fuentes de datos ahora están configuradas y listas para utilizarse en el recorrido.
