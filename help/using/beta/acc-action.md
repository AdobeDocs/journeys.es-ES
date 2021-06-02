---
product: adobe campaign
title: Acerca de la integración de Campaign Classic
description: Obtenga información sobre la integración de Campaign Classic
hide: true
hidefromtoc: true
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 6%

---

# Integración con Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Esta integración le permite enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Classic.

La conexión entre las instancias de Journey Orchestration y Campaign Classic se configura por Adobe en el momento del aprovisionamiento.

>[!CAUTION]
>
> Esta integración se presenta como una versión beta privada. No está disponible para todos los clientes Journey Orchestration.

## Notas importantes

* No hay restricciones en los mensajes. Se limita el número de mensajes que se pueden enviar a 50.000/hora en función de nuestro actual SLA de Campaign Classic. Por este motivo, la organización de Recorridos solo debe utilizarse en casos de uso unitario (eventos individuales, no segmentos).

* Debe configurar una acción en el lienzo por plantilla que desee utilizar.

* Le recomendamos que utilice una instancia del Centro de mensajes dedicada que esté alojada para esta integración para evitar afectar a otras operaciones del Campaign Classic que pueda estar realizando. El servidor de marketing puede alojarse o alojarse de forma local. La compilación necesaria es Candidate de la versión 21.1.

* No hay validación de que la carga útil o el mensaje del Campaign Classic sean correctos.

* No puede utilizar una acción de Campaign Classic con una calificación de segmento.

## Requisitos previos

En Campaign Classic, debe crear y publicar un mensaje transaccional y su evento asociado. Consulte la [documentación de Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Póngase en contacto con el Adobe para obtener la carga útil JSON correspondiente a cada mensaje. A continuación, pegue esta carga útil al configurar la acción en el Journey Orchestration (consulte a continuación).

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

## Configuración de la acción

En Journey Orchestration, debe configurar una acción por mensaje transaccional. Siga estos pasos:

1. Cree una nueva acción. Consulte esta [sección](../action/action.md).
1. Introduzca un nombre y una descripción.
1. En el campo **Action type**, seleccione **Adobe Campaign Classic**.
1. Haga clic en el campo **Payload** y pegue un ejemplo de la carga útil JSON correspondiente al mensaje del Campaign Classic. Póngase en contacto con el Adobe para obtener esta carga útil.
1. Ajuste los distintos campos. Algunos campos, como los parámetros de canal y los campos de personalización (ctx), deben definirse como variables.
1. Haga clic en **Save**.

![](../assets/accintegration1.png)

Para cada acción configurada, hay una actividad de acción disponible en la paleta Diseñador de recorridos.

## Adición de un mensaje en un recorrido

1. Diseñe el recorrido, empezando por un evento . Consulte esta [sección](../building-journeys/journey.md).
1. En la sección **Action** de la paleta, seleccione una acción del Campaign Classic y agréguela al recorrido.
1. En **Action parameters**, se muestran todos los campos esperados en la carga útil del mensaje. Debe asignar cada uno de estos campos al campo que desee utilizar, ya sea desde el evento o desde el origen de datos. Esto es similar a las acciones personalizadas. Consulte esta [sección](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
