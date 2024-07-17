---
product: adobe campaign
solution: Journey Orchestration
title: Envío de un mensaje mediante Campaign v7/v8
description: Envío de un mensaje mediante Campaign v7/v8
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# Envío de un mensaje mediante Campaign v7/v8 {#campaign-classic-use-case}

Este caso de uso presenta todos los pasos necesarios para enviar un correo electrónico mediante la integración con Adobe Campaign Classic v7 y Adobe Campaign v8.

Primero crearemos una plantilla de correo electrónico transaccional en Campaign. Luego, en Journey Orchestration, crearemos el evento, la acción y diseñaremos el recorrido.

Para obtener más información sobre la integración de Campaign, consulte estas páginas:

* [Creación de una acción de campaña](../action/acc-action.md)
* [Usando la acción en un recorrido](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

La instancia de Campaign debe estar aprovisionada para esta integración. Es necesario configurar la función Mensajería transaccional.

1. Inicie sesión en la instancia de control de Campaign.

1. En **Administración** > **Plataforma** > **Enumeraciones**, seleccione la enumeración **Tipo de evento** (eventType). Cree un nuevo tipo de evento (&quot;evento de recorrido&quot;, en nuestro ejemplo). Tendrá que utilizar el nombre interno del tipo de evento al escribir el archivo JSON más adelante.

   ![](../assets/accintegration-uc-1.png)

1. Desconecte y vuelva a conectarse a la instancia para que la creación sea eficaz.

1. En **Centro de mensajes** > **Plantillas de mensajes transaccionales**, cree una nueva plantilla de correo electrónico basada en el tipo de evento creado anteriormente.

   ![](../assets/accintegration-uc-2.png)

1. Diseñe la plantilla. En este ejemplo, utilizamos la personalización del nombre del perfil y el número de pedido. El nombre se encuentra en la fuente de datos de Adobe Experience Platform y el número de pedido es un campo del evento del Journey Orchestration. Asegúrese de utilizar los nombres de campo correctos en Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publish su plantilla transaccional.

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

* Para el canal, debe escribir &quot;correo electrónico&quot;.
* Para eventType, utilice el nombre interno del tipo de evento creado anteriormente.
* La dirección de correo electrónico es una variable, por lo que puede escribir cualquier etiqueta.
* En ctx, los campos de personalización también son variables.

**Journey Orchestration**

1. En primer lugar, debe crear un evento. Asegúrese de incluir el campo purchaseOrderNumber.

   ![](../assets/accintegration-uc-5.png)

1. A continuación, debe crear en Journey Orchestration una acción que corresponda a la plantilla de Campaign. En la lista desplegable **Tipo de acción**, seleccione **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Haga clic en **Campo de carga útil** y pegue el JSON creado anteriormente.

   ![](../assets/accintegration-uc-7.png)

1. Para la dirección de correo electrónico y los dos campos personalizados, cambie **Constant** a **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Ahora cree un nuevo recorrido e inicie con el evento creado anteriormente.

   ![](../assets/accintegration-uc-9.png)

1. Añada la acción y asigne cada campo al campo correcto en Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Agregue una actividad **End** y pruebe su recorrido.

   ![](../assets/accintegration-uc-11.png)

1. Ahora puede publicar el recorrido.
