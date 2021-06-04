---
product: adobe campaign
title: Trabajar con Adobe Campaign
description: Obtenga información sobre las acciones de Adobe Campaign
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 4%

---

# Trabajar con Adobe Campaign {#using_adobe_campaign}

## Uso de Adobe Campaign Standard {#using_adobe_campaign_standard}

Puede enviar correos electrónicos, notificaciones push y SMS utilizando las funciones de mensajería transaccional de Adobe Campaign Standard.

[!DNL Journey Orchestration] viene con una acción predeterminada que permite la conexión a Adobe Campaign Standard.

El mensaje transaccional del Campaign Standard y su evento asociado deben publicarse para poder utilizarlo en el Journey Orchestration. Si el evento se publica pero el mensaje no lo es, no será visible en la interfaz del Journey Orchestration. Si el mensaje se publica pero su evento asociado no lo es, será visible en la interfaz del Journey Orchestration, pero no se podrá utilizar.

>[!NOTE]
>
>Una regla de límite de 13 llamadas por segundo se define automáticamente para las acciones de Adobe Campaign Standard en cuanto se configura la integración con Adobe Campaign Standard. Esto corresponde a la escala oficial de la mensajería transaccional de Adobe Campaign Standard.
>
>Obtenga más información sobre los SLA de mensajería transaccional en [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Estos son los pasos para configurarlo:

1. En la lista **[!UICONTROL Actions]**, haga clic en la acción **[!UICONTROL AdobeCampaignStandard]** integrada. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/actioncampaign.png)

1. Copie la URL de la instancia de Adobe Campaign Standard y péguela en el campo **[!UICONTROL URL]** .

1. Haga clic en **[!UICONTROL Test the instance URL]** para probar la validez de la instancia.

   >[!NOTE]
   >
   >Esta prueba comprueba que:
   >
   >El host es &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; o &quot;.adls.adobe.com&quot;.
   >
   >La dirección URL empieza por https,
   >
   >El ORG asociado a esta instancia de Adobe Campaign Standard es el mismo que el ORG del Journey Orchestration.

Al diseñar el recorrido, habrá tres acciones disponibles en la categoría **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de acciones de Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **El evento de** reacciones también le permite reaccionar en los clics del mensaje, las aperturas, etc. (consulte [Reactions events](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Si utiliza un sistema de terceros para enviar mensajes, debe agregar y configurar una acción personalizada. Consulte [Acerca de la configuración de acciones personalizadas](../action/about-custom-action-configuration.md).

## Uso de Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

Esta integración está disponible para Adobe Campaign Classic v7 a partir de la versión 21.1 y Adobe Campaign v8. Le permite enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign.

La conexión entre el Journey Orchestration y las instancias de Campaign se configura por Adobe en el momento del aprovisionamiento.

En esta [sección](../usecase/campaign-v7-v8-use-case.md) se presenta un caso de uso completo.

Para cada acción configurada, hay una actividad de acción disponible en la paleta Diseñador de recorridos. Consulte esta [sección](../building-journeys/using-adobe-campaign-actions.md).

### Notas importantes

* No hay restricciones en los mensajes. Se limita el número de mensajes que se pueden enviar a 50 000/hora en función de nuestro SLA de Campaign actual. Por este motivo, la organización de Recorridos solo debe utilizarse en casos de uso unitario (eventos individuales, no segmentos).

* Debe configurar una acción en el lienzo por plantilla que desee utilizar. Debe configurar una acción en Journey Orchestration para cada plantilla que desee utilizar desde Adobe Campaign.

* Le recomendamos que utilice una instancia del Centro de mensajes dedicada que esté alojada para esta integración para evitar afectar a otras operaciones de Campaign que pueda estar realizando. El servidor de marketing puede alojarse o alojarse de forma local. La compilación necesaria es candidata para la versión 21.1 o buena.

* No hay validación de que la carga útil o el mensaje de Campaign sean correctos.

* No puede utilizar una acción de Campaign con un evento de calificación de segmentos.

### Requisitos previos

En Campaign, debe crear y publicar un mensaje transaccional y su evento asociado. Consulte la [documentación de Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Puede crear la carga útil JSON correspondiente a cada mensaje siguiendo el patrón a continuación. A continuación, pegue esta carga útil al configurar la acción en el Journey Orchestration (consulte a continuación)

Este es un ejemplo.

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **canal**: el canal definido para la plantilla transaccional de Campaign
* **eventType**: el nombre interno del evento de Campaign
* **ctx**: en función de la personalización que tenga en el mensaje.

### Configuración de la acción

En Journey Orchestration, debe configurar una acción por mensaje transaccional. Siga estos pasos:

1. Cree una nueva acción. Consulte esta [sección](../action/action.md).
1. Introduzca un nombre y una descripción.
1. En el campo **Action type**, seleccione **Adobe Campaign Classic**.
1. Haga clic en el campo **Payload** y pegue un ejemplo de la carga útil JSON correspondiente al mensaje de Campaign. Póngase en contacto con el Adobe para obtener esta carga útil.
1. Ajuste los distintos campos para que sean estáticos o variables en función de si desea asignarlos en el lienzo de Recorrido. Ciertos campos, como los parámetros de canal para la dirección de correo electrónico y los campos de personalización (ctx), probablemente desee definirlos como variables para la asignación en el contexto del recorrido.
1. Haga clic en **Save**.

![](../assets/accintegration1.png)


