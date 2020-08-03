---
title: journeystep eventos campos comunes
description: journeystep eventos campos comunes
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# journeystep eventos campos comunes {#sharing-common-fields}

Esta mezcla se compartirá con los eventos travelStepEvent y travelStepProfileEvent.

Estos son los campos XDM comunes que [!DNL Journey Orchestration] se envían a Adobe Experience Platform. Los campos comunes se enviarán para cada paso que se procese en un viaje. Se utilizan campos más específicos para acciones y enriquecimientos personalizados.

Algunos de estos campos solo están disponibles en patrones de procesamiento específicos (ejecución de acciones, captura de datos, etc.) para limitar el tamaño de los eventos.

## entrada

Indica si el usuario ha entrado en el viaje. Si no está presente, suponemos que el valor es false.

Tipo: booleano

Valores: true/false

## reingreso

Indica si el usuario ha vuelto a entrar en el viaje con la misma instancia. Si no está presente, suponemos que el valor es false.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica si la instancia ha finalizado (correctamente o no).

Tipo: booleano

## eventID

ID de Evento en proceso para el procesamiento de pasos. Si el evento es externo, el valor es eventId. Si el evento es interno, el valor es el eventId interno (como scheduleNotificationReceived, executeAction, etc.).

Tipo: string

## nodeID

Id. de nodo de cliente (del lienzo).

Tipo: string

## stepID

ID única del paso que se está procesando.

Tipo: string

## stepName

Name of the step that is currently being processed.

Tipo: string

## stepType

Tipo del paso.

Tipo: string

Valores posibles:

* Condición
* Acción
* Planificador
* Temporizador

## stepStatus

Estado del paso, que representa el estado del paso, cuando se ha procesado (y se ha activado el evento de paso).

Tipo: string

El estado puede ser:

* finalizó: el paso no tiene transición y su procesamiento ha finalizado correctamente.
* error: el procesamiento de pasos ha generado un error.
* transiciones: el paso está esperando un evento para la transición a otro paso.
* capped: el paso ha fallado en un error de límite, generado durante una acción o enriquecimiento.
* timedout: el paso falló en un error de tiempo de espera, generado durante una acción o enriquecimiento.
* instanceTimedout: the step has stopped its processing, because the instance has reached its timeout.

## journeyID

ID del viaje.

Tipo: string

## journeyVersionID

ID of the journey version. This id represents the identity reference to the journey, in the case of the journeyStepEvent.

Tipo: string

## journeyVersionName

Nombre de la versión del viaje.

Tipo: string

## travelVersion

Versión del viaje.

Tipo: string

## instanceID

ID interna de la instancia de viaje.

Tipo: string

## externalKey

Clave externa extraída del evento para procesarla.

Tipo: string

## parentStepID

ID de paso del elemento principal del paso procesado actual en la instancia.

Tipo: string

## parentStepName

Nombre del paso principal del paso actual.

Tipo: string

## parentTransitionID

Id. de la transición que ha llevado la instancia al paso procesado.

Tipo: string

## parentTransitionName

Nombre de la transición que ha llevado la instancia al paso procesado.

Tipo: string

## inTest

Indicated if this journey is in test mode or not.

Tipo: booleano

## processingTime

Cantidad total de tiempo en milisegundos desde la entrada del paso de instancia hasta el final del procesamiento.

Tipo: long

## instanceType

Indica el tipo de instancia, si es por lotes o unitarios.

Tipo: string

Valores: lote/unidad

## recurrenceIndex

Índice de la periodicidad si el viaje es por lotes y recurrente (la primera ejecución tiene un índice de periodicidad = 1).

Tipo: long

## isBatchToUnitary

Indica si esta instancia unitaria se ha activado desde una instancia de lote.

Tipo: booleano

## batchExternalKey

External Key for batch event.

Tipo: string

## batchInstanceID

this is the batch instance ID.

Tipo: string

## batchUnitaryBranchID

si la instancia se ha activado desde una instancia de lote, ID de rama unitaria.

Tipo: string
