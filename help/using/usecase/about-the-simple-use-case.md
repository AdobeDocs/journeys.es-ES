---
product: adobe campaign
title: Acerca del caso de uso simple
description: Obtenga más información sobre el caso de uso simple de recorrido
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 3af822bacfd1a5a53ec7280dff1136d77b90c809
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 9%

---

# Acerca del caso de uso simple{#concept_grh_vby_w2b}

## Objetivo {#purpose}

Veamos el ejemplo de una marca de hotel llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las áreas estratégicas: vestíbulo, pisos, restaurante, gimnasio, piscina, etc.

En este caso de uso, veremos cómo enviar un mensaje personalizado en tiempo real a una persona que camina junto a una señalización situada cerca del spa.

Queremos enviar un mensaje solo si la persona es mujer. El mensaje debe recibirse en segundos.

![](../assets/journeyuc1_16.png)

## Requisitos previos {#prerequisites}

Para nuestro caso de uso, hemos diseñado una plantilla de mensajería transaccional de correo electrónico en Adobe Campaign Standard. Estamos utilizando una plantilla de mensajería transaccional de eventos. Consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html).

Adobe Campaign Standard está configurado para enviar correos electrónicos.

Los eventos se envían desde el teléfono móvil de los clientes cuando se detectan cerca de una señalización. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.
