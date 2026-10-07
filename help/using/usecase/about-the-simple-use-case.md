---
product: adobe campaign
title: Acerca del caso de uso simple
description: Descubra más información sobre el caso de uso sencillo del recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
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
source-wordcount: '236'
ht-degree: 36%
---
# Acerca del caso de uso simple{#concept_grh_vby_w2b}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


## Objetivo {#purpose}

Veamos el ejemplo de una marca hotelera llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las áreas estratégicas: vestíbulo, pisos, restaurante, gimnasio, piscina, etc.

En este ejemplo de uso, veremos cómo enviar un mensaje personalizado en tiempo real a una persona que camina junto a una baliza colocada cerca del spa.

Queremos enviar un mensaje solo si la persona es una mujer. El mensaje debe recibirse en segundos.

![](../assets/journeyuc1_16.png)

## Requisitos previos {#prerequisites}

Para nuestro caso de uso, hemos diseñado una plantilla de mensajería transaccional de correo electrónico en Adobe Campaign Standard. Se está utilizando una plantilla de mensajería transaccional de eventos. Consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=es).

Adobe Campaign Standard está configurado para enviar correos electrónicos.

Los eventos se envían desde el teléfono móvil de los clientes cuando se detectan cerca de una baliza. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.
