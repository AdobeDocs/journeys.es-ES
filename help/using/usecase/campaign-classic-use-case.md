---
product: adobe campaign
solution: Journey Orchestration
title: Envío de un mensaje mediante Campaign v7/v8
description: Envío de un mensaje mediante Campaign v7/v8
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 3e78e429bbdfc95bfef74e0f2e2b92f8ff17cfdb
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# Envío de un mensaje mediante Campaign v7/v8 {#campaign-classic-use-case}

Este caso de uso presenta todos los pasos necesarios para enviar un correo electrónico mediante la integración con Adobe Campaign Classic v7 y Adobe Campaign v8.

We will first create a transactional email template in Campaign. Then, in Journey Orchestration, we&#39;ll create the event, action and design the journey.

Para obtener más información sobre la integración de Campaign, consulte estas páginas:

* [Creación de una acción de campaña](../action/acc-action.md)
* [Using the action in a journey](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

La instancia de Campaign debe aprovisionarse para esta integración. La función Mensajería transaccional debe configurarse.

1. Log in to your Campaign control instance.

1. Under **Administration** > **Platform** > **Enumerations**, select the **Event type** (eventType) enumeration. Cree un nuevo tipo de evento (&quot;recorrido-evento&quot;, en nuestro ejemplo). Deberá utilizar el nombre interno del tipo de evento al escribir el archivo JSON más adelante.

   ![](../assets/accintegration-uc-1.png)

1. Desconecte y vuelva a conectar con la instancia para que la creación sea efectiva.

1. En **Centro de mensajes** > **Plantillas de mensajes transaccionales**, cree una nueva plantilla de correo electrónico basada en el tipo de evento creado anteriormente.

   ![](../assets/accintegration-uc-2.png)

1. Diseñe la plantilla. En este ejemplo, se utiliza la personalización en el nombre del perfil y el número de pedido. The first name is in the Adobe Experience Platform data source, and the order number is a field from our Journey Orchestration event. Asegúrese de utilizar los nombres de campo correctos en Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publish your transactional template.

   ![](../assets/accintegration-uc-4.png)

1. Ahora debe escribir la carga útil JSON correspondiente a la plantilla.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* For the channel, you need to type &quot;email&quot;.
* For the eventType, use the internal name of the event type created previously.
* The email address will be a variable, so you can type any label.
* Under ctx, the personalization fields are also variables.

**Journey Orchestration**

1. En primer lugar, debe crear un evento. Asegúrese de incluir el campo &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. A continuación, debe crear, en Journey Orchestration, una acción correspondiente a la plantilla de campaña. En el **Tipo de acción** desplegable, seleccione **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Click the **Payload field** and paste the JSON created previously.

   ![](../assets/accintegration-uc-7.png)

1. Para la dirección de correo electrónico y los dos campos de personalización, cambie **Constante** a **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Ahora cree un nuevo recorrido y comience con el evento creado anteriormente.

   ![](../assets/accintegration-uc-9.png)

1. Añada la acción y asigne cada campo al campo correcto en el Journey Orchestration .

   ![](../assets/accintegration-uc-10.png)

1. Agregue un **Fin** y pruebe el recorrido.

   ![](../assets/accintegration-uc-11.png)

1. You can now publish your journey.
