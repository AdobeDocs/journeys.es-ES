---
title: Trabajar con Adobe Campaign
description: Información sobre las acciones de Adobe Campaign
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6685565797a6cdc43b9c8fc39c9354ae6d213f1f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---


# Trabajar con Adobe Campaign {#using_adobe_campaign_standard}

Puede enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional del Adobe Campaign Standard.

[!DNL Journey Orchestration] viene con una acción lista para usar que permite la conexión al Adobe Campaign Standard.

El mensaje transaccional del Campaign Standard y su evento asociado deben publicarse para su uso en Journey Orchestration. Si el evento se publica pero el mensaje no, no será visible en la interfaz del Journey Orchestration. Si el mensaje se publica pero su evento asociado no, será visible en la interfaz del Journey Orchestration pero no se podrá utilizar.

>[!NOTE]
>
>Para evitar la sobrecarga de la mensajería transaccional de Adobe Campaign Standard, se recomienda configurar una regla **de** límite para la integración de Campaign Standard.
>
>Obtenga más información sobre los SLA de mensajería transaccional en la Descripción [del producto de](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard.

Estos son los pasos para configurarlo:

1. En la **[!UICONTROL Actions]** lista, haga clic en la **[!UICONTROL AdobeCampaignStandard]** acción integrada. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/actioncampaign.png)

1. Copie la URL de la instancia de Adobe Campaign Standard y péguela en el **[!UICONTROL URL]** campo.

1. Haga clic en el **[!UICONTROL Test the instance URL]** para probar la validez de la instancia.

   >[!NOTE]
   >
   >Esta prueba comprueba que:
   >
   >* El host es &quot;.campaña.adobe.com&quot; o &quot;.campaña-sandbox.adobe.com&quot;,
   >* La URL inicio con https,
   >* El ORG asociado a la instancia de este Adobe Campaign Standard es el mismo que el ORG del Journey Orchestration.


Al diseñar el viaje, habrá tres acciones disponibles en la **[!UICONTROL Action]** categoría: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de acciones](../building-journeys/using-adobe-campaign-actions.md)de Adobe Campaign). **El evento** de reacciones también le permitirá reaccionar en los clics de mensajes, aperturas, etc. (consulte [eventos](../building-journeys/event-activities.md#section_dhx_gss_dgb)de reacciones).

![](../assets/journey58.png)

Si utiliza un sistema de terceros para enviar mensajes, debe agregar y configurar una acción personalizada. See [About custom action configuration](../action/about-custom-action-configuration.md).
