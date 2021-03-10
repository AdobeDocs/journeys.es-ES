---
product: adobe campaign
solution: Journey Orchestration
title: Limitaciones de Journey Orchestration
description: Obtenga más información sobre las limitaciones de Journey Orchestration
translation-type: tm+mt
source-git-commit: 1433ccabaceb31c7ffac117a31531d0d380a54f8
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 2%

---


# Limitaciones {#limitations}

Estas son limitaciones relacionadas con el uso de Journey Orchestration.

## Limitaciones generales de acciones

* No hay restricciones de envío. 
* En caso de error, se realizan sistemáticamente dos reintentos. No se puede ajustar el número de reintentos según el mensaje de error recibido. 
* El evento **Reaction** integrado le permite reaccionar ante las acciones integradas (consulte esta [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 
* No hay integración de productos de Adobe Campaign Classic.

## Limitaciones de las versiones de Journey {#journey-versions-limitations}

* un recorrido que comienza con una actividad de evento en v1 no puede comenzar con otra cosa que un evento en versiones posteriores. No se puede iniciar un recorrido con un evento **Segment Qualification**.
* un recorrido que comience con una actividad **Segment Qualification** en v1 siempre debe comenzar con **Segment Qualification** en versiones posteriores.
* El segmento y el área de nombres elegidos en **Segment qualification** (primer nodo) no se pueden cambiar en las nuevas versiones.
* La regla de reentrada debe ser la misma en todas las versiones del recorrido.

## Clasificación del segmento {#segment-qualification}

* La actividad **Segment qualification** no se puede usar junto con la mensajería transaccional de Adobe Campaign Standard debido a restricciones de rendimiento. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de acciones personalizadas

* La dirección URL de acción personalizada no admite parámetros dinámicos. 
* Solo se admiten los métodos de llamada POST y PUT. 
* El nombre del parámetro de consulta o del encabezado no debe comenzar por &quot;.&quot; o &quot;$&quot;. 
* No se permiten direcciones IP. 
* Direcciones internas de Adobe (.adobe). no están permitidos.
 

## Limitaciones de las acciones de Adobe Campaign

* La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo en todos los canales de una instancia determinada. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de eventos

* Para los eventos generados por el sistema, los datos de flujo utilizados para iniciar un recorrido del cliente deben configurarse primero dentro de Journey Orchestration para obtener un ID de organización único. Este ID de organización debe añadirse a la carga útil de flujo continuo que llega a Adobe Experience Platform. Esta limitación no se aplica a los eventos basados en reglas.
 

## Limitaciones de las fuentes de datos

* Las fuentes de datos externas se pueden aprovechar en un recorrido del cliente para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.

## Recorridos que comienzan al mismo tiempo que una creación de perfil {#journeys-limitation-profile-creation}

En Adobe Experience Platform hay un retraso asociado con la creación/actualización de perfiles basados en API. El objetivo de nivel de servicio (SLT) en términos de latencia es &lt; 1 min desde la ingesta hasta el perfil unificado para el percentil 95 de las solicitudes, a un volumen de 20 000 solicitudes por segundo (RPS).

Si un Recorrido se activa simultáneamente para crear un perfil y comprueba o recupera inmediatamente información del servicio de perfil, es posible que no funcione correctamente.

Puede elegir entre una de estas dos soluciones:

* Agregue una actividad de espera después del primer evento para que Adobe Experience Platform tenga el tiempo necesario para realizar la ingesta en el servicio de perfil.

* Configure un recorrido que no aproveche inmediatamente el perfil. Por ejemplo, si el recorrido está diseñado para confirmar la creación de una cuenta, el evento de experiencia podría contener la información necesaria para enviar el primer mensaje de confirmación (nombre, apellidos, dirección de correo electrónico, etc.).