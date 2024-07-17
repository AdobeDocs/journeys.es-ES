---
product: adobe campaign
title: Acerca del caso de uso simple
description: Descubra más información sobre el caso de uso sencillo del recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 9%

---

# Acerca del caso de uso simple{#concept_grh_vby_w2b}

## Objetivo {#purpose}

Veamos el ejemplo de una marca hotelera llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las áreas estratégicas: vestíbulo, pisos, restaurante, gimnasio, piscina, etc.

En este ejemplo de uso, veremos cómo enviar un mensaje personalizado en tiempo real a una persona que camina junto a una baliza colocada cerca del spa.

Queremos enviar un mensaje solo si la persona es una mujer. El mensaje debe recibirse en segundos.

![](../assets/journeyuc1_16.png)

## Requisitos previos {#prerequisites}

Para nuestro caso de uso, hemos diseñado una plantilla de mensajería transaccional de correo electrónico en Adobe Campaign Standard. Se está utilizando una plantilla de mensajería transaccional de eventos. Consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=es).

Adobe Campaign Standard está configurado para enviar correos electrónicos.

Los eventos se envían desde el teléfono móvil de los clientes cuando se detectan cerca de una baliza. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.
