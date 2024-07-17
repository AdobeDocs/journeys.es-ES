---
product: adobe campaign
title: Acerca de la integración de las versiones 7 y 8 de Campaign
description: Obtenga información acerca de la integración de las versiones 7 y 8 de Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 13%

---

# Uso de Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Esta integración está disponible para Adobe Campaign Classic v7 a partir de la versión 21.1 y para Adobe Campaign v8. Permite enviar correos electrónicos, notificaciones push y SMS mediante las funcionalidades de mensajería transaccional de Adobe Campaign.

La conexión entre las instancias de Journey Orchestration y Campaign se configura por Adobe en el momento del aprovisionamiento.

Se presenta un caso de uso de extremo a extremo en esta [sección](../usecase/campaign-classic-use-case.md).

Para cada acción configurada, hay una actividad de acción disponible en la paleta del diseñador de recorridos. Consulte esta [sección](../building-journeys/using-adobe-campaign-classic.md).

## Notas importantes

* No se restringen los mensajes. Reducimos el número de mensajes que se pueden enviar a más de 50 000/hora según nuestro SLA de Campaign actual. Por este motivo, la orquestación de Recorrido solo debe utilizarse en casos de uso unitarios (eventos individuales, no segmentos).

* Debe configurar una acción en el lienzo por plantilla que desee utilizar. Debe configurar una acción en Journey Orchestration para cada plantilla que desee utilizar desde Adobe Campaign.

* Le recomendamos que utilice una instancia del Centro de mensajes dedicada que esté alojada para esta integración para evitar afectar a otras operaciones de Campaign que pueda tener en marcha. El servidor de marketing puede estar alojado o ser local. La versión requerida es 21.1 Release Candidate o superior.

* No se ha validado que la carga útil o el mensaje de Campaign sean correctos.

* No puede utilizar una acción de Campaign con un evento de calificación de segmentos.

## Requisitos previos

En Campaign, es necesario crear y publicar un mensaje transaccional y su evento asociado. Consulte la [documentación de Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Puede crear la carga útil JSON correspondiente a cada mensaje siguiendo el patrón siguiente. A continuación, pegue esta carga útil al configurar la acción en Journey Orchestration (a continuación)

Vea el siguiente ejemplo:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **canal**: el canal definido para su plantilla transaccional de Campaign
* **eventType**: el nombre interno del evento de Campaign
* **ctx**: variable basada en la personalización que tiene en el mensaje.

## Configuración de la acción

En Journey Orchestration, debe configurar una acción por mensaje transaccional. Siga estos pasos:

1. Cree una nueva acción. Consulte esta [sección](../action/action.md).
1. Introduzca un nombre y una descripción.
1. En el campo **Tipo de acción**, seleccione **Adobe Campaign Classic**.
1. Haga clic en el campo **Carga útil** y pegue un ejemplo de la carga útil JSON correspondiente al mensaje de Campaign. Póngase en contacto con el Adobe para obtener esta carga útil.
1. Ajuste los distintos campos para que sean estáticos o variables, según si desea asignarlos en el lienzo de Recorrido. Algunos campos, como los parámetros de canal para la dirección de correo electrónico y los campos de personalización (ctx), probablemente desee definirlos como variables para su asignación en el contexto del recorrido.
1. Haga clic en **Guardar**.

![](../assets/accintegration1.png)


