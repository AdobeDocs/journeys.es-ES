---
product: adobe campaign
solution: Journey Orchestration
title: Limitaciones del Journey Orchestration
description: Obtenga más información sobre las limitaciones de los Journey Orchestration
translation-type: tm+mt
source-git-commit: f562d4a967e6551d3b8a1bc4dbddbf01da9b3e70
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 2%

---


# Limitaciones {#limitations}

Estas son las limitaciones relacionadas con el uso de Journey Orchestration.

## Limitaciones de acciones generales

* No hay limitación de envío. 
* En caso de error se realizan dos reintentos de forma sistemática. No se puede ajustar el número de reintentos según el mensaje de error recibido. 
* El evento integrado **Reacción** le permite reaccionar a las acciones predeterminadas (consulte esta [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 
* No hay integración de productos de Adobe Campaign Classic.

## Limitaciones de versiones de recorrido {#journey-versions-limitations}

* un recorrido que comienza con una actividad de evento en v1 no puede inicio con otra cosa que un evento en versiones posteriores. No se puede inicio un recorrido con un evento **Calificación del segmento**.
* un recorrido que comienza con una actividad **Calificación del segmento** en v1 siempre debe estar en inicio con una **Calificación del segmento** en versiones posteriores.
* El segmento y la Área de nombres elegidos en **Calificación del segmento** (primer nodo) no se pueden cambiar en las nuevas versiones.
* La regla de reentrada debe ser la misma en todas las versiones de recorrido.

## Calificación del segmento {#segment-qualification}

* La actividad **Calificación del segmento** no se puede usar junto con la mensajería transaccional de Adobe Campaign Standard debido a restricciones de rendimiento. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de acciones personalizadas

* La URL de acción personalizada no admite parámetros dinámicos. 
* Solo se admiten los métodos de llamada POST y PUT. 
* El nombre del parámetro de consulta o del encabezado no debe tener inicio con &quot;.&quot; o &quot;$&quot;. 
* No se permiten direcciones IP. 
* Direcciones de Adobe internas (.adobe.) no se permiten.
 

## Limitaciones de acciones de Adobe Campaign

* La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo en canales para una instancia determinada. Consulte [Descripción del producto de Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitaciones de eventos

* Los datos de flujo utilizados para iniciar un recorrido del cliente deben configurarse primero dentro del Journey Orchestration para obtener un ID de orquestación único. Este identificador de orquestación debe agregarse a la carga útil de flujo que llega a Adobe Experience Platform.
 

## Limitaciones de fuentes de datos

* Las fuentes de datos externas se pueden aprovechar dentro de un recorrido del cliente para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.

## Recorridos que comienzan al mismo tiempo que una creación de perfil {#journeys-limitation-profile-creation}

Existe un retraso asociado a la creación o actualización de perfiles basados en API en Adobe Experience Platform. El Destinatario de nivel de servicio (SLT) en términos de latencia es &lt; 1 min desde la ingestión hasta el Perfil unificado para el 95 % de las solicitudes, a un volumen de 20 000 solicitudes por segundo (RPS).

Si un Recorrido se activa de forma simultánea a la creación de un perfil y comprueba o recupera inmediatamente la información del servicio de Perfil, es posible que no funcione correctamente.

Puede elegir una de estas dos soluciones:

* Añada una actividad de espera después del primer evento para que Adobe Experience Platform tenga el tiempo necesario para realizar la ingestión en el servicio de Perfil.

* Configure un recorrido que no aproveche inmediatamente el perfil. Por ejemplo, si el recorrido está diseñado para confirmar la creación de una cuenta, el evento de experiencias puede contener la información necesaria para enviar el primer mensaje de confirmación (nombre, apellidos, dirección de correo electrónico, etc.).