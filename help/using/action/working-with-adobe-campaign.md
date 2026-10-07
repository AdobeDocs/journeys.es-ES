---
product: adobe campaign
title: Uso de Adobe Campaign
description: Más información sobre las acciones de Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 17%
---
# Uso de Adobe Campaign Standard {#using_adobe_campaign_standard}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


Puede enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard.

[!DNL Journey Orchestration] viene con una acción predeterminada que permite la conexión a Adobe Campaign Standard.

El mensaje transaccional de Campaign Standard y su evento asociado deben publicarse para poder utilizarse en Journey Orchestration. Si el evento se publica pero el mensaje no, no será visible en la interfaz de Journey Orchestration. Si el mensaje se publica pero su evento asociado no, estará visible en la interfaz de Journey Orchestration, pero no se podrá utilizar.

>[!NOTE]
>
>Una regla de límite de 4000 llamadas por 5 minutos se define automáticamente para las acciones de Adobe Campaign Standard en cuanto se configura la integración de Adobe Campaign Standard. Esto corresponde a la escala oficial de Adobe Campaign Standard Transactional Messaging.
>
>Obtenga más información sobre los SLA de mensajería transaccional en [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/es/legal/product-descriptions/campaign-standard.html).

Estos son los pasos para configurarlo:

1. En la lista **[!UICONTROL Actions]**, haga clic en la acción integrada **[!UICONTROL AdobeCampaignStandard]**. El panel de configuración de acción se abre en el lado derecho de la pantalla.

   ![](../assets/actioncampaign.png)

1. Copie la URL de instancia de Adobe Campaign Standard y péguela en el campo **[!UICONTROL URL]**.

1. Haga clic en **[!UICONTROL Test the instance URL]** para probar la validez de la instancia.

   >[!NOTE]
   >
   >Esta prueba comprueba lo siguiente:
   >
   >El host es &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; o &quot;.adls.adobe.com&quot;.
   >
   >La dirección URL comienza con https,
   >
   >La ORG asociada a la instancia de este Adobe Campaign Standard es la misma que la ORG de Journey Orchestration.

Al diseñar el recorrido, habrá tres acciones disponibles en la categoría **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de acciones de Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **El evento de reacciones** también le permitirá reaccionar ante clics en mensajes, aperturas, etc. (consulte [Eventos de reacciones](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Si utiliza un sistema de terceros para enviar mensajes, debe agregar y configurar una acción personalizada. Consulte [Acerca de la configuración de acciones personalizadas](../action/about-custom-action-configuration.md).
