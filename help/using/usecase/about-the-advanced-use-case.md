---
title: Acerca del caso de uso avanzado
description: Obtenga más información sobre el caso de uso avanzado del viaje
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# Acerca del caso de uso avanzado{#concept_vzy_ncy_w2b}

## Objetivo {#purpose}

Veamos el ejemplo de una marca de hotel llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las zonas estratégicas: vestíbulo, plantas, restaurante, gimnasio, piscina, etc.

>[!NOTE]
>
>En este caso de uso, utilizamos Adobe Campaign Standard para enviar mensajes.

En este caso de uso, veremos cómo enviar mensajes personalizados en tiempo real a los clientes cuando caminen cerca de una señalización específica.

En primer lugar, queremos enviar un mensaje tan pronto como una persona entre en un hotel de Marlton. Queremos enviar un mensaje sólo si la persona no ha recibido ninguna comunicación de nosotros en las últimas 24 horas.

Luego comprobamos dos condiciones:

* Si esta persona no es miembro leal, le enviamos un correo electrónico para unirse a la oferta de fidelidad.
* Si esta persona ya es miembro leal, comprobamos si tiene una reserva de habitación:
   * Si no lo hace, le enviamos una notificación push con las tarifas de habitación.
   * Si lo hace, le enviamos una notificación push de bienvenida. Y si entra al restaurante en las siguientes 6 horas, le enviamos una notificación push con descuento en una comida.

![](../assets/journeyuc2_29.png)

Para este caso de uso, será necesario crear dos eventos (consulte [](../usecase/configuring-the-events.md)):

* El evento de señalización del vestíbulo que se lanzará al sistema cuando un cliente entre en el hotel.
* El evento de señalización del restaurante que se iniciará cuando un cliente entre en el restaurante.

Será necesario configurar una conexión a dos fuentes de datos (consulte [](../usecase/configuring-the-data-sources.md)):

* El origen de datos integrado de la plataforma de experiencias, para recuperar la información de nuestras dos condiciones (pertenencia de lealtad y fecha de contacto anterior), así como la información de personalización del mensaje.
* El sistema de reservación del hotel, para recuperar la información de estado de la reserva.

## Requisitos previos {#prerequisites}

En nuestro caso de uso, hemos diseñado tres plantillas de mensajería transaccional de Adobe Campaign Standard. Estamos utilizando plantillas de mensajería transaccional de eventos. Consulte [esta página](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard está configurado para enviar correos electrónicos y notificaciones push.

El ID de Experience Cloud se utiliza como clave para identificar al cliente en el sistema de reservas de hotel.

Los eventos se envían desde el teléfono móvil del cliente cuando se detectan cerca de una señalización. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.

El campo de miembro Lealtad es un campo personalizado y se agregó en XDM para nuestro ID de organización específico.
