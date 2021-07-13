---
product: adobe campaign
title: Configuración de las fuentes de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso avanzado de recorrido
feature: Recorridos
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# Configuración de las fuentes de datos {#concept_vml_hdy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También tenemos que comprobar si la persona es un miembro socio y no ha sido contactada en las últimas 24 horas. Esta información se almacena en la base de datos Perfil del cliente en tiempo real. El **usuario técnico** debe configurar la fuente de datos de Adobe Experience Platform para recuperar esos campos.

Para obtener más información sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Data Sources]** y seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. En los campos de grupo preconfigurados, compruebe que los siguientes campos estén seleccionados:

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un esquema **[!UICONTROL Profiles]** y añada el campo **Loyalty member** para nuestra condición. El campo **Loyalty member** es un campo personalizado y se agregó en XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un esquema **[!UICONTROL ExperienceEvent]** y elija los campos necesarios para nuestra condición en el número de mensajes enviados en un periodo determinado: _marca de tiempo_ para la fecha y _directMarketing > envía > valor_ para el número de mensajes enviados.

   ![](../assets/journeyuc2_7.png)

1. Haga clic en **[!UICONTROL Save]**.

También tenemos que comprobar si la persona tiene una reserva en el sistema de reservas de hotel. El **usuario técnico** debe configurar una segunda fuente de datos para recuperar este campo.

1. En la lista de fuentes de datos, haga clic en **[!UICONTROL Add]** para agregar una nueva fuente de datos externa para definir la conexión con su sistema de reservas de hotel.

   ![](../assets/journeyuc2_9.png)

1. Introduzca un nombre para la fuente de datos y la URL del servicio externo, por ejemplo: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Recomendamos encarecidamente utilizar HTTPS por motivos de seguridad.

1. Configure la autenticación según la configuración del servicio externo: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. En nuestro ejemplo, elegimos &quot;Básico&quot; para el tipo y especificamos el nombre de usuario y la contraseña para la llamada de API.

   ![](../assets/journeyuc2_10.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]** para definir la información que se va a recuperar y los parámetros de la API. Para nuestro ejemplo, solo hay un parámetro (el id), por lo que necesitamos crear un grupo de campos con la siguiente información:

   * **[!UICONTROL Method]**: seleccione el método POST o GET. En nuestro caso, seleccionamos el método GET.
   * **[!UICONTROL Cache duration]**: esto varía según la frecuencia de las llamadas a la API. En nuestro caso, el sistema de reservas se actualiza cada 10 minutos.
   * **[!UICONTROL Response Payload]**: haga clic dentro del  **[!UICONTROL Payload]** campo y pegue un ejemplo de la carga útil. Compruebe que los tipos de campo son correctos. Cada vez que se llama a la API, el sistema recupera todos los campos incluidos en el ejemplo de carga útil. En nuestro ejemplo, la carga útil solo contiene el estado de reserva:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: introduzca el parámetro correspondiente a la clave utilizada para identificar a cada cliente, &quot;id&quot; en nuestro ejemplo. El valor de este parámetro se define en el recorrido .

   ![](../assets/journeyuc2_11.png)

1. Haga clic en **[!UICONTROL Save]**.

   Las fuentes de datos ahora están configuradas y listas para utilizarse en el recorrido.
