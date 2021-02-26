---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de la integración de Campaign Classic
description: Obtenga información sobre la integración de Campaign Classic
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 937b7235d41fe7f0395e303736974e32eea8558f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Integración con Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Esta integración le permite enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería transaccional de Adobe Campaign Classic.

La conexión entre las instancias de Journey Orchestration y Campaign Classic se configura por Adobe en el momento del aprovisionamiento.

>[!CAUTION]
>
> Esta integración se presenta como una versión beta privada. No está disponible para todos los clientes Journey Orchestration.

## Notas importantes

* No hay limitación de mensajes. Limitamos el número de mensajes que se pueden enviar a 50.000/hora según nuestro nivel de servicio Campaign Classic actual. Por este motivo, la orquestación de Recorrido solo debe utilizarse en casos de uso unitario (eventos individuales, no segmentos).

* Debe configurar una acción en el lienzo por plantilla que desee utilizar.

* Le recomendamos que utilice una instancia de centro de mensajes dedicada que esté alojada para esta integración a fin de evitar afectar a otras operaciones de Campaign Classic que pueda haber llevado a cabo. El servidor de mercadotecnia puede alojarse o estar in situ. La compilación requerida es 21.1 Release Candidate.

* No hay ninguna validación de que la carga útil o el mensaje de Campaign Classic sean correctos.

* No puede utilizar una acción de Campaign Classic con una cualificación de segmento.

## Requisitos previos

En Campaign Classic, debe crear y publicar un mensaje transaccional y su evento asociado. Consulte la [documentación de Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Póngase en contacto con Adobe para obtener la carga útil JSON correspondiente a cada mensaje. Después pegará esta carga útil al configurar la acción en Journey Orchestration (ver más abajo).

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
1. Escriba un nombre y una descripción.
1. En el campo **Tipo de acción**, seleccione **Adobe Campaign Classic**.
1. Haga clic en el campo **Carga útil** y pegue un ejemplo de la carga útil JSON correspondiente al mensaje de Campaign Classic. Póngase en contacto con Adobe para obtener esta carga útil.
1. Ajuste los distintos campos. Determinados campos, como los parámetros de canal y los campos de personalización (ctx), deben definirse como variables.
1. Haga clic en **Save**.

![](../assets/accintegration1.png)

Para cada acción configurada, hay una actividad de acción disponible en la paleta Diseñador de recorridos.

## Añadir un mensaje en un recorrido

1. Diseñe su recorrido, empezando por un evento. Consulte esta [sección](../building-journeys/journey.md).
1. En la sección **Acción** de la paleta, seleccione una acción de Campaign Classic y agréguela al recorrido.
1. En los **parámetros de acción**, se muestran todos los campos esperados en la carga útil del mensaje. Debe asignar cada uno de estos campos al campo que desee utilizar, ya sea desde el evento o desde el origen de datos. Esto es similar a las acciones personalizadas. Consulte esta [sección](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

