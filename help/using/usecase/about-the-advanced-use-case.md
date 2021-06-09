---
product: adobe campaign
title: Acerca del caso de uso avanzado
description: Más información sobre el caso de uso avanzado de recorrido
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 3af822bacfd1a5a53ec7280dff1136d77b90c809
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 4%

---

# Acerca del caso de uso avanzado{#concept_vzy_ncy_w2b}

## Objetivo {#purpose}

Veamos el ejemplo de una marca de hotel llamada Marlton. En sus hoteles, han colocado dispositivos de señalización cerca de todas las áreas estratégicas: vestíbulo, pisos, restaurante, gimnasio, piscina, etc.

>[!NOTE]
>
>En este caso de uso, utilizamos Adobe Campaign Standard para enviar mensajes.

En este caso de uso, veremos cómo enviar mensajes personalizados en tiempo real a los clientes cuando caminen cerca de una señalización específica.

En primer lugar, queremos enviar un mensaje tan pronto como una persona entre en un hotel de Marlton. Queremos enviar un mensaje sólo si la persona no ha recibido ninguna comunicación de nosotros en las últimas 24 horas.

Luego comprobamos dos condiciones:

* Si esta persona no es un miembro socio, le enviamos un correo electrónico para unirse a la oferta de membresía de fidelidad.
* Si esta persona ya es miembro socio, comprobamos si tiene una reserva de habitación:
   * Si no lo hace, le enviamos una notificación push con tarifas de habitación.
   * Si lo hace, le enviamos una notificación push de bienvenida. Y si entra al restaurante dentro de las próximas 6 horas, le enviamos una notificación push con un descuento en una comida.

![](../assets/journeyuc2_29.png)

Para este caso de uso, necesitamos crear dos eventos (consulte [esta página](../usecase/configuring-the-events.md)):

* El evento de señalización del vestíbulo que será transferido al sistema cuando un cliente entre al hotel.
* El evento de señalización del restaurante que se impulsará cuando un cliente entre en el restaurante.

Será necesario configurar una conexión con dos fuentes de datos (consulte [esta página](../usecase/configuring-the-data-sources.md)):

* La fuente de datos integrada de Adobe Experience Platform, para recuperar la información de nuestras dos condiciones (pertenencia de fidelidad y fecha de último contacto), así como la información de personalización del mensaje.
* El sistema de reservas de hotel, para recuperar la información del estado de reserva.

## Requisitos previos {#prerequisites}

Para nuestro caso de uso, hemos diseñado tres plantillas de mensajería transaccional de Adobe Campaign Standard. Estamos utilizando plantillas de mensajería transaccional de eventos. Consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html).

Adobe Campaign Standard está configurado para enviar correos electrónicos y notificaciones push.

El ID de Experience Cloud se utiliza como clave para identificar al cliente en el sistema de reservas de hotel.

Los eventos se envían desde el teléfono móvil de los clientes cuando se detectan cerca de una señalización. Debe diseñar una aplicación móvil para enviar eventos desde el teléfono móvil del cliente al SDK móvil.

El campo miembro Lealtad es un campo personalizado y se agregó en XDM para nuestro ID de organización específico.
