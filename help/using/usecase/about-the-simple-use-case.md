---
product: adobe campaign
solution: Journey Orchestration
title: Acerca del caso de uso simple
description: Obtenga más información sobre el caso de uso simple del viaje
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 14%

---


# Acerca del caso de uso simple{#concept_grh_vby_w2b}

## Objetivo {#purpose}

Veamos el ejemplo de una marca de hotel llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las zonas estratégicas: vestíbulo, plantas, restaurante, gimnasio, piscina, etc.

En este caso de uso, veremos cómo enviar un mensaje personalizado en tiempo real a una persona que camina junto a una señalización situada cerca del spa.

Queremos enviar un mensaje sólo si la persona es una mujer. El mensaje debe recibirse en segundos.

![](../assets/journeyuc1_16.png)

## Requisitos previos {#prerequisites}

Para nuestro caso de uso, hemos diseñado una plantilla de mensajería transaccional de correo electrónico en Adobe Campaign Standard. Estamos utilizando una plantilla de mensajería transaccional de evento. Consulte [esta página](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

Adobe Campaign Standard está configurado para enviar correos electrónicos.

Los eventos se envían desde el teléfono móvil del cliente cuando se detectan cerca de una señalización. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.