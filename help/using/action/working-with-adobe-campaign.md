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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%

---


# Trabajar con Adobe Campaign {#using_adobe_campaign_standard}

Puede enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Standard.

[!DNL Journey Orchestration] viene con una acción lista para usar que permite la conexión a Adobe Campaign Standard. Estos son los pasos para configurarlo:

1. En la **[!UICONTROL Actions]** lista, haga clic en la **[!UICONTROL AdobeCampaignStandard]** acción integrada. El panel de configuración de acciones se abre en el lado derecho de la pantalla.

   ![](../assets/actioncampaign.png)

1. Copie la URL de la instancia de Adobe Campaign Standard y péguela en el **[!UICONTROL URL]** campo.

1. Haga clic en el **[!UICONTROL Test the instance URL]** para probar la validez de la instancia.

Al diseñar el viaje, habrá tres acciones disponibles en la **[!UICONTROL Action]** categoría: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (véase [](../building-journeys/using-adobe-campaign-actions.md)).

![](../assets/journey58.png)

Si utiliza un sistema de terceros para enviar mensajes, debe agregar y configurar una acción personalizada. Consulte [](../action/about-custom-action-configuration.md).
