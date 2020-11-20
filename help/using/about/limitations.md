---
product: adobe campaign
solution: Journey Orchestration
title: Limitaciones del Journey Orchestration
description: Obtenga más información sobre las limitaciones de los Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Limitaciones {#limitations}

Estas son las limitaciones relacionadas con el uso de Journey Orchestration.

## Limitaciones de acciones generales

* No hay limitación de envío. 
* En caso de error se realizan dos reintentos de forma sistemática. No se puede ajustar el número de reintentos según el mensaje de error recibido. 
* El evento de **reacción** integrado le permite reaccionar a las acciones integradas (consulte esta [página](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado. 
* No hay integración de productos de Adobe Campaign Classic.
 
## Limitaciones de acciones personalizadas

* La URL de acción personalizada no admite parámetros dinámicos. 
* Solo se admiten los métodos de llamada POST y PUT. 
* El nombre del parámetro de consulta o del encabezado no debe tener inicio con &quot;.&quot; o &quot;$&quot;. 
* No se permiten direcciones IP. 
* Direcciones de Adobe internas (.adobe.) no se permiten.
 

## Limitaciones de acciones de Adobe Campaign

* La mensajería transaccional de Adobe Campaign Standard tiene una escala de 50 000 mensajes por hora como máximo en canales para una instancia determinada. Consulte Descripción [del producto de](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard. 
* La actividad **de calificación** de segmentos no debe usarse junto con la mensajería transaccional de Adobe Campaign Standard debido a las restricciones de rendimiento.
 
## Limitaciones de eventos

* Los datos de flujo utilizados para iniciar un viaje del cliente deben configurarse primero dentro del Journey Orchestration para obtener un ID de orquestación único. Este identificador de orquestación debe agregarse a la carga útil de flujo que llega a Adobe Experience Platform.
 

## Limitaciones de fuentes de datos

* Las fuentes de datos externas se pueden aprovechar en un viaje del cliente para buscar datos externos en tiempo real. Estas fuentes deben utilizarse mediante la API de REST, admiten JSON y pueden gestionar el volumen de solicitudes.