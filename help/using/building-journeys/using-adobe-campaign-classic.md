---
product: adobe campaign
solution: Journey Orchestration
title: Uso de acciones de Adobe Campaign
description: Obtenga información sobre las acciones de Adobe Campaign
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 9%

---

# Uso de Adobe Campaign Classic {#using_campaign_classic}

Una integración está disponible si tiene Adobe Campaign Classic. Le permitirá enviar correos electrónicos, notificaciones push y SMS utilizando las funciones de mensajería transaccional de Adobe Campaign Classic.

La conexión entre las instancias de Journey Orchestration y Campaign Classic se configura por Adobe en el momento del aprovisionamiento. Adobe de contacto.

Para que esto funcione, debe configurar una acción dedicada. Consulte esta [sección](../action/acc-action.md).

En esta [sección](../usecase/campaign-classic-use-case.md) se presenta un caso de uso completo.

1. Diseñe el recorrido, empezando por un evento . Consulte esta [sección](../building-journeys/journey.md).
1. En la sección **Action** de la paleta, seleccione una acción del Campaign Classic y agréguela al recorrido.
1. En **Action parameters**, se muestran todos los campos esperados en la carga útil del mensaje. Debe asignar cada uno de estos campos al campo que desee utilizar, ya sea desde el evento o desde el origen de datos. Esto es similar a las acciones personalizadas. Consulte esta [sección](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
