---
product: adobe campaign
title: Limitaciones del Journey Orchestration
description: Obtenga más información sobre las limitaciones de los Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 18c94897b5cea0d92a83f36845fdda64220b668f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 57%

---

# Limitaciones {#limitations}

Estas son limitaciones relacionadas con el uso de Journey Orchestration.

## Protecciones generales del recorrido {#journeys-guardrails-journeys}

* El número de actividades de un recorrido está limitado a 50. El número de actividades se muestra en la sección superior izquierda del lienzo de recorrido.
* El número de **recorridos en directo** en una organización está limitada a 100 por simulador de pruebas. Cuando se alcanza este límite, ya no se puede publicar un nuevo recorrido.

## Limitaciones generales de acciones

* No hay restricciones de envío. 
* En caso de error, se realizan tres reintentos de forma sistemática. No puede ajustar el número de reintentos según el mensaje de error recibido. 
* El **Reacción** le permite reaccionar a las acciones integradas (consulte esta [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 

## Limitaciones de las versiones de recorrido {#journey-versions-limitations}

* Un recorrido que se inicia con una actividad de evento en v1 no puede comenzar con otra cosa que un evento en versiones posteriores. No puede iniciar un recorrido con un evento de **Calificación de segmentos**.
* Un recorrido que se inicia con una actividad de **Calificación de segmentos** en v1 siempre debe comenzar con una **Calificación de segmentos** en versiones posteriores.
* El segmento y el área de nombres elegidos en **Clasificación del segmento** (primer nodo) no se puede cambiar en las versiones nuevas.
* La regla de reentrada debe ser la misma en todas las versiones del recorrido.

## Clasificación del segmento {#segment-qualification}

* La variable **Clasificación del segmento** no se puede usar junto con la mensajería transaccional de Adobe Campaign Standard debido a restricciones de rendimiento. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de acciones personalizadas

* La URL de acción personalizada no admite parámetros dinámicos. 
* Solo se admiten los métodos de llamada de POST y PUT. 
* El nombre del parámetro de consulta o del encabezado no debe comenzar con &quot;.&quot; o &quot;$&quot;. 
* No se permiten direcciones IP. 
* Las direcciones de Adobe internas (.adobe.) no se permiten.
 

## Limitaciones de las acciones de Adobe Campaign

* La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo en todos los canales de una instancia determinada. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de eventos

* En el caso de los eventos generados por el sistema, los datos de flujo utilizados para iniciar un recorrido de cliente deben configurarse primero en el Journey Orchestration para obtener un ID de organización único. Este ID de orquestación debe añadirse a la carga útil de streaming que llega a Adobe Experience Platform. Esta limitación no se aplica a los eventos basados en reglas.
 

## Limitaciones de las fuentes de datos

* Las fuentes de datos externas se pueden aprovechar dentro de un recorrido de clientes para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.

## Recorridos que comienzan al mismo tiempo que la creación de perfiles {#journeys-limitation-profile-creation}

Hay un retraso asociado a la creación/actualización de perfiles basados en la API en Adobe Experience Platform. El destinatario de nivel de servicio (SLT) en términos de latencia es &lt;1 min desde la ingesta hasta el perfil unificado para el percentil 95 de las solicitudes, a un volumen de 20 000 solicitudes por segundo (RPS).

Si un Recorrido se activa simultáneamente para crear un perfil y comprueba o recupera inmediatamente la información del servicio de perfil, es posible que no funcione correctamente.

Puede elegir entre una de estas dos soluciones:

* Agregue una actividad de espera después del primer evento para que Adobe Experience Platform tenga el tiempo necesario para realizar la ingesta en el servicio de perfil.

* Configure un recorrido que no utilice inmediatamente el perfil. Por ejemplo, si el recorrido está diseñado para confirmar la creación de una cuenta, el evento de experiencia podría contener la información necesaria para enviar el primer mensaje de confirmación (nombre, apellidos, dirección de correo electrónico, etc).
