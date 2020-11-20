---
product: adobe campaign
solution: Journey Orchestration
title: journeystep eventos campos comunes
description: journeystep eventos campos comunes
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# journeysteps events common fields {#sharing-common-fields}

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

ID de evento en proceso para el procesamiento de pasos. Si el evento es externo, el valor es eventId. Si el evento es interno, el valor es el eventId interno (como scheduleNotificationReceived, executeAction, etc.).

Tipo: string

## nodeID

Id. de nodo de cliente (del lienzo).

Tipo: string

## stepID

ID única del paso que se está procesando.

Tipo: string

## stepName

Nombre del paso que se está procesando.

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
* error: the step processing has raised an error.
* transiciones: el paso está esperando un evento para la transición a otro paso.
* capped: el paso ha fallado en un error de límite, generado durante una acción o enriquecimiento.
* timedout: el paso ha fallado en un error de tiempo de espera, generado durante una acción o enriquecimiento.
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

Se indica si este viaje está en modo de prueba o no.

Tipo: booleano

## processingTime

Total amount of time in milliseconds from the instance step entrance to the end of the processing.

Tipo: long

## instanceType

Indicates the instance type, if it is batch or unitary.

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

si la instancia se ha activado desde una instancia de lote, ID de rama unitaria.

Tipo: string
