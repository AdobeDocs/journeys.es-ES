---
product: adobe campaign
title: Acerca de la integración de Campaign Classic
description: Obtenga información sobre la integración de Campaign Classic
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 1712529984af02d0a3f678418db1e819370056d6
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---

# Uso de Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Esta integración le permite enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Classic.

La conexión entre las instancias de Journey Orchestration y Campaign Classic se configura por Adobe en el momento del aprovisionamiento.

En esta [sección](../usecase/campaign-classic-use-case.md) se presenta un caso de uso completo.

Para cada acción configurada, hay una actividad de acción disponible en la paleta Diseñador de recorridos. Consulte esta [sección](../building-journeys/using-adobe-campaign-classic.md).

## Notas importantes

* No hay restricciones en los mensajes. Se limita el número de mensajes que se pueden enviar a 50.000/hora en función de nuestro actual SLA de Campaign Classic. Por este motivo, la organización de Recorridos solo debe utilizarse en casos de uso unitario (eventos individuales, no segmentos).

* Debe configurar una acción en el lienzo por plantilla que desee utilizar. Debe configurar una acción en Journey Orchestration para cada plantilla que desee utilizar desde Adobe Campaign Classic.

* Le recomendamos que utilice una instancia del Centro de mensajes dedicada que esté alojada para esta integración para evitar afectar a otras operaciones del Campaign Classic que pueda estar realizando. El servidor de marketing puede alojarse o alojarse de forma local. La compilación necesaria es candidata para la versión 21.1 o buena.

* No hay validación de que la carga útil o el mensaje del Campaign Classic sean correctos.

* No puede utilizar una acción de Campaign Classic con un evento de calificación de segmentos.

## Requisitos previos

En Campaign Classic, debe crear y publicar un mensaje transaccional y su evento asociado. Consulte la [documentación de Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Puede crear la carga útil JSON correspondiente a cada mensaje siguiendo el patrón a continuación. A continuación, pegue esta carga útil al configurar la acción en el Journey Orchestration (consulte a continuación)

Este es un ejemplo.

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

* **canal**: el canal definido para la plantilla transaccional de Campaign Classic
* **eventType**: el nombre interno del evento de Campaign Classic
* **ctx**: en función de la personalización que tenga en el mensaje.

## Configuración de la acción

En Journey Orchestration, debe configurar una acción por mensaje transaccional. Siga estos pasos:

1. Cree una nueva acción. Consulte esta [sección](../action/action.md).
1. Introduzca un nombre y una descripción.
1. En el campo **Action type**, seleccione **Adobe Campaign Classic**.
1. Haga clic en el campo **Payload** y pegue un ejemplo de la carga útil JSON correspondiente al mensaje del Campaign Classic. Póngase en contacto con el Adobe para obtener esta carga útil.
1. Ajuste los distintos campos para que sean estáticos o variables en función de si desea asignarlos en el lienzo de Recorrido. Ciertos campos, como los parámetros de canal para la dirección de correo electrónico y los campos de personalización (ctx), probablemente desee definirlos como variables para la asignación en el contexto del recorrido.
1. Haga clic en **Save**.

![](../assets/accintegration1.png)


