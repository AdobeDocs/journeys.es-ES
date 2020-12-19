---
product: adobe campaign
solution: Journey Orchestration
title: Limitaciones del Journey Orchestration
description: Obtenga más información sobre las limitaciones de los Journey Orchestration
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Limitaciones {#limitations}

Estas son las limitaciones relacionadas con el uso de Journey Orchestration.

## Limitaciones de acciones generales

* No hay limitación de envío. 
* En caso de error se realizan dos reintentos de forma sistemática. No se puede ajustar el número de reintentos según el mensaje de error recibido. 
* El evento integrado **Reacción** le permite reaccionar a las acciones predeterminadas (consulte esta [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 
* No hay integración de productos de Adobe Campaign Classic.

## Limitaciones de versiones de viajes {#journey-versions-limitations}

* un viaje que comienza con una actividad de evento en v1 no puede inicio con otra cosa que un evento en versiones posteriores. No se puede inicio un viaje con un evento **Calificación del segmento**.
* un viaje que comienza con una actividad de **Calificación del segmento** en v1 siempre debe tener un inicio con una **Calificación del segmento** en versiones posteriores.
* El segmento y la Área de nombres elegidos en **Calificación del segmento** (primer nodo) no se pueden cambiar en las nuevas versiones.
* La regla de reentrada debe ser la misma en todas las versiones del viaje.

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

* Los datos de flujo utilizados para iniciar un viaje del cliente deben configurarse primero dentro del Journey Orchestration para obtener un ID de orquestación único. Este identificador de orquestación debe agregarse a la carga útil de flujo que llega a Adobe Experience Platform.
 

## Limitaciones de fuentes de datos

* Las fuentes de datos externas se pueden aprovechar en un viaje del cliente para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.