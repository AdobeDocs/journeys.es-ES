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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---


# journeystep eventos campos comunes {#sharing-common-fields}

Esta mezcla se compartirá con los eventos travelStepEvent y travelStepProfileEvent.

Estos son los campos comunes de XDM que la orquestación de viajes envía a la plataforma de datos de Adobe. Los campos comunes se enviarán para cada paso que se procese en un viaje. Se utilizan campos más específicos para acciones y enriquecimientos personalizados.

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

Type of the step.

Tipo: string

Valores posibles:

* Condition
* Acción
* Planificador
* Temporizador

## stepStatus

Status of the step, representing the status of the step, when its processing has been done (and the step event fired).

Tipo: string

El estado puede ser:

* finalizó: el paso no tiene transición y su procesamiento ha finalizado correctamente.
* error: the step processing has raised an error.
* transiciones: el paso está esperando un evento para la transición a otro paso.
* capped: el paso ha fallado en un error de límite, generado durante una acción o enriquecimiento.
* timedout: el paso falló en un error de tiempo de espera, generado durante una acción o enriquecimiento.
* instanceTimedout: el paso ha detenido su procesamiento porque la instancia ha alcanzado su tiempo de espera.

## travelID

ID del viaje.

Tipo: string

## travelVersionID

ID de la versión del viaje. Esta identificación representa la referencia de identidad del viaje, en el caso de la función travelStepEvent.

Tipo: string

## travelVersionName

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

Step ID of the parent of the current processed step in the instance.

Tipo: string

## parentStepName

Step name of the parent of the current step.

Tipo: string

## parentTransitionID

Id of the transition which has brought the instance to the processed step.

Tipo: string

## parentTransitionName

Nombre de la transición que ha llevado la instancia al paso procesado.

Tipo: string

## inTest

Se indica si este viaje está en modo de prueba o no.

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

es el ID de instancia de lote.

Tipo: string

## batchUnitaryBranchID

if the instance has been triggered from a batch instance, unitary branch ID.

Tipo: string
