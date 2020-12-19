---
product: adobe campaign
solution: Journey Orchestration
title: Configuración de las fuentes de datos
description: Aprenda a configurar la fuente de datos para el caso de uso avanzado del viaje
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 14%

---


# Configuración de las fuentes de datos {#concept_vml_hdy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También tenemos que comprobar si la persona es miembro de fidelidad y no ha sido contactada en las últimas 24 horas. Esta información se almacena en la base de datos de Perfil del cliente en tiempo real. El **usuario técnico** debe configurar el origen de datos de Adobe Experience Platform para recuperar esos campos.

Para obtener información adicional sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el menú superior, haga clic en la ficha **[!UICONTROL Data Sources]** y seleccione el origen de datos de Adobe Experience Platform integrado.

   ![](../assets/journey23.png)

1. En los campos de grupo preconfigurados, compruebe que los siguientes campos están seleccionados:

   * _persona > nombre > nombre_
   * _persona > nombre > apellido_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un esquema **[!UICONTROL Profiles]** y agregue el campo **miembro de lealtad** para nuestra condición. El campo **miembro de lealtad** es un campo personalizado y se agregó en XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]**, seleccione un esquema **[!UICONTROL ExperienceEvent]** y elija los campos necesarios para nuestra condición en el número de mensajes enviados en un período determinado: _marca de hora_ para la fecha y _directMarketing > envía > valor_ para el número de mensajes enviados.

   ![](../assets/journeyuc2_7.png)

1. Haga clic en **[!UICONTROL Save]**.

También tenemos que comprobar si la persona tiene una reserva en el sistema de reservas del hotel. El **usuario técnico** debe configurar un segundo origen de datos para recuperar este campo.

1. En lista de fuentes de datos, haga clic en **[!UICONTROL Add]** para agregar una nueva fuente de datos externa para definir la conexión con su sistema de reservación de hoteles.

   ![](../assets/journeyuc2_9.png)

1. Escriba un nombre para el origen de datos y la dirección URL del servicio externo, por ejemplo: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Recomendamos encarecidamente utilizar HTTPS por motivos de seguridad.

1. Configure la autenticación según la configuración del servicio externo: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. En nuestro ejemplo, elegimos &quot;Básico&quot; para el tipo y especificamos el nombre de usuario y la contraseña para la llamada de API.

   ![](../assets/journeyuc2_10.png)

1. Haga clic en **[!UICONTROL Add a New Field Group]** para definir la información que se va a recuperar y los parámetros de API. Para nuestro ejemplo, solo hay un parámetro (la identificación), por lo que necesitamos crear un grupo de campos con la siguiente información:

   * **[!UICONTROL Method]**: seleccione el método POST o GET. En nuestro caso, seleccionamos el método GET.
   * **[!UICONTROL Cache duration]**:: esto varía según la frecuencia de las llamadas a la API. En nuestro caso, el sistema de reservas se actualiza cada 10 minutos.
   * **[!UICONTROL Response Payload]**:: haga clic dentro del  **[!UICONTROL Payload]** campo y pegue un ejemplo de la carga útil. Compruebe que los tipos de campo son correctos. Cada vez que se llama a la API, el sistema recupera todos los campos incluidos en el ejemplo de carga útil. En nuestro ejemplo, la carga útil solo contiene el estado de reserva:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:: introduzca el parámetro correspondiente a la clave utilizada para identificar a cada cliente, &quot;id&quot; en nuestro ejemplo. El valor de este parámetro se definirá en el viaje.

   ![](../assets/journeyuc2_11.png)

1. Haga clic en **[!UICONTROL Save]**.

   Las fuentes de datos ahora están configuradas y listas para utilizarse en su viaje.
