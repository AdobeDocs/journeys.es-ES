---
product: adobe campaign
title: Trabajar con Adobe Campaign
description: Obtenga información sobre las acciones de Adobe Campaign
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Uso de Adobe Campaign Standard {#using_adobe_campaign_standard}

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
