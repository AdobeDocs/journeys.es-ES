---
product: adobe campaign
solution: Journey Orchestration
title: Trabajar con Adobe Campaign
description: Información sobre las acciones de Adobe Campaign
translation-type: tm+mt
source-git-commit: 723c30865a5039bd68a8ac2e45d4c87a760e694d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---


# Trabajar con Adobe Campaign {#using_adobe_campaign_standard}

Puede enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard.

[!DNL Journey Orchestration] viene con una acción lista para usar que permite la conexión a Adobe Campaign Standard.

El mensaje transaccional del Campaign Standard y su evento asociado deben publicarse para su uso en Journey Orchestration. Si el evento se publica pero el mensaje no, no será visible en la interfaz del Journey Orchestration. Si el mensaje se publica pero su evento asociado no, será visible en la interfaz del Journey Orchestration pero no se podrá utilizar.

>[!NOTE]
>
>La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo en canales para una instancia determinada. Para reducir el riesgo de sobrecarga, le recomendamos que configure una **regla de límite** para la integración de Campaign Standard.
>
>Obtenga más información sobre los SLA de mensajería transaccional en [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Estos son los pasos para configurarlo:

1. En la lista **[!UICONTROL Actions]**, haga clic en la acción **[!UICONTROL AdobeCampaignStandard]** integrada. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/actioncampaign.png)

1. Copie la URL de la instancia de Adobe Campaign Standard y péguela en el campo **[!UICONTROL URL]**.

1. Haga clic en **[!UICONTROL Test the instance URL]** para probar la validez de la instancia.

   >[!NOTE]
   >
   >Esta prueba comprueba que:
   >
   >El host es &quot;.campaña.adobe.com&quot;, &quot;.campaña-sandbox.adobe.com&quot; o &quot;campaña-demo.adobe.com&quot;
   >
   >La URL inicio con https,
   >
   >El ORG asociado a esta instancia de Adobe Campaign Standard es el mismo que el ORG del Journey Orchestration.

Al diseñar el recorrido, habrá tres acciones disponibles en la categoría **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de acciones de Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Los** eventos de reacciones también le permitirán reaccionar en los clics de mensajes, aperturas, etc. (consulte [eventos de reacciones](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Si utiliza un sistema de terceros para enviar mensajes, debe agregar y configurar una acción personalizada. Consulte [Acerca de la configuración de acciones personalizadas](../action/about-custom-action-configuration.md).
