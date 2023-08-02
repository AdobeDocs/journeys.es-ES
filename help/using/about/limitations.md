---
product: adobe campaign
title: Limitaciones del Journey Orchestration
description: Más información sobre las limitaciones de los Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 66%

---

# Limitaciones {#limitations}

Estas son las limitaciones relacionadas con el uso de Journey Orchestration.

## Protecciones generales del recorrido {#journeys-guardrails-journeys}

* El número de actividades en un recorrido ahora está limitado a 50. El número de actividades se muestra en la sección superior izquierda del lienzo de recorrido.
* El número de **recorridos en directo** en una organización está limitado ahora a 100 por zona protegida. Cuando se alcanza este límite, ya no se puede publicar un nuevo recorrido.

## Limitaciones generales de las acciones

* En caso de error, se realizan tres reintentos de forma sistemática. No puede ajustar el número de reintentos según el mensaje de error recibido. 
* La función integrada **Reacción** Este evento le permite reaccionar a las acciones listas para usar (consulte esto [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 

## Limitaciones de versiones de recorrido {#journey-versions-limitations}

* Un recorrido que se inicia con una actividad de evento en v1 no puede comenzar con otra cosa que un evento en versiones posteriores. No puede iniciar un recorrido con un evento de **Calificación de segmentos**.
* Un recorrido que se inicia con una actividad de **Calificación de segmentos** en v1 siempre debe comenzar con una **Calificación de segmentos** en versiones posteriores.
* El segmento y el área de nombres elegidos en **Calificación de segmentos** (primer nodo) no se puede cambiar en las nuevas versiones.
* La regla de reentrada debe ser la misma en todas las versiones del recorrido.

## Clasificación del segmento {#segment-qualification}

* El **Calificación de segmentos** La actividad no se puede usar junto con la mensajería transaccional de Adobe Campaign Standard debido a restricciones de rendimiento. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## Limitaciones de acciones personalizadas

* La URL de acción personalizada no admite parámetros dinámicos. 
* Solo se admiten los métodos de llamada de POST y PUT. 
* El nombre del parámetro de consulta o del encabezado no debe comenzar con &quot;.&quot; o &quot;$&quot;. 
* No se permiten direcciones IP. 
* Las direcciones de Adobe internas (.adobe.) no se permiten.
 
## Limitaciones de acciones de Adobe Campaign

* La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo entre canales para una instancia determinada. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 
## Limitaciones de eventos

* En el caso de los eventos generados por el sistema, los datos de streaming utilizados para iniciar un recorrido de cliente deben configurarse primero en Journey Orchestration para obtener un ID de orquestación único. Este ID de orquestación debe añadirse a la carga útil de streaming que llega a Adobe Experience Platform. Esta limitación no se aplica a los eventos basados en reglas.
 
## Limitaciones de fuentes de datos

* Las fuentes de datos externas se pueden aprovechar dentro de un recorrido de cliente para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.

## Recorridos que comienzan al mismo tiempo que la creación de un perfil {#journeys-limitation-profile-creation}

Hay un retraso asociado a la creación/actualización de perfiles basados en la API en Adobe Experience Platform. El destinatario de nivel de servicio (SLT) en términos de latencia es &lt;1 min desde la ingesta hasta el perfil unificado para el percentil 95 de las solicitudes, a un volumen de 20 000 solicitudes por segundo (RPS).

Si un Recorrido se activa simultáneamente para crear un perfil y comprueba o recupera inmediatamente la información del servicio de perfil, es posible que no funcione correctamente.

Puede elegir entre una de estas dos soluciones:

* Agregue una actividad de espera después del primer evento para que Adobe Experience Platform tenga el tiempo necesario para realizar la ingesta en el servicio de perfil.

* Configure un recorrido que no utilice inmediatamente el perfil. Por ejemplo, si el recorrido está diseñado para confirmar la creación de una cuenta, el evento de experiencia podría contener la información necesaria para enviar el primer mensaje de confirmación (nombre, apellidos, dirección de correo electrónico, etc).
