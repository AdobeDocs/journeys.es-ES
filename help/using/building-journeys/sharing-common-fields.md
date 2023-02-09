---
product: adobe campaign
title: campos comunes de los eventos de los recorridos
description: campos comunes de los eventos de los recorridos
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# campos comunes de los eventos de los recorridos {#sharing-common-fields}

Esta mezcla la compartirán journeyStepEvent y journeyStepProfileEvent.

Estos son los campos XDM comunes que [!DNL Journey Orchestration] envía a Adobe Experience Platform. Se enviarán campos comunes para cada paso que se procese en un recorrido. Se utilizan campos más específicos para acciones y enriquecimientos personalizados.

Algunos de estos campos solo están disponibles en patrones de procesamiento específicos (ejecución de acciones, recuperación de datos, etc.) para limitar el tamaño de los eventos.

## entrada

Indica si el usuario ha introducido el recorrido. Si no está presente, supongamos que el valor es falso.

Tipo: booleano

Valores: true/false

## reentrada

Indica si el usuario ha vuelto a entrar en el recorrido con la misma instancia. Si no está presente, supongamos que el valor es falso.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica si la instancia ha finalizado (con éxito o no).

Tipo: booleano

## eventID

ID de evento en procesamiento, para el procesamiento de pasos. Si el evento es externo, el valor es eventId. Si el evento es interno, el valor es el eventId interno (como scheduledNotificationReceived, executeAction, etc.).

Tipo: cadena

## nodeID

ID de nodo de cliente (desde el lienzo).

Tipo: cadena

## stepID

ID único del paso que se está procesando actualmente.

Tipo: cadena

## stepName

Nombre del paso que se está procesando actualmente.

Tipo: cadena

## stepType

Tipo del paso.

Tipo: cadena

Valores posibles:

* Condición
* Acción
* Planificador
* Temporizador

## stepStatus

Estado del paso, que representa el estado del paso, cuándo se ha completado su procesamiento (y el evento de paso se ha activado).

Tipo: cadena

El estado puede ser el siguiente:

* finalizado: el paso no tiene transición y su procesamiento ha finalizado correctamente.
* error: el procesamiento de pasos ha generado un error.
* transiciones: el paso está esperando a que un evento pase a otro paso.
* límite: el paso ha fallado en un error de restricción, producido durante una acción o enriquecimiento.
* tiempo de espera: el paso ha fallado en un error de tiempo de espera, producido durante una acción o enriquecimiento.
* instanceTimedout: el paso ha detenido su procesamiento, ya que la instancia ha alcanzado su tiempo de espera.

## journeyID

ID del recorrido.

Tipo: cadena

## journeyVersionID

ID de la versión de recorrido. Este id representa la referencia de identidad al recorrido, en el caso de journeyStepEvent.

Tipo: cadena

## journeyVersionName

Nombre de la versión de recorrido.

Tipo: cadena

## journeyVersion

Versión de la versión de recorrido.

Tipo: cadena

## instanceID

ID interno de la instancia de recorrido.

Tipo: cadena

## externalKey

Clave externa extraída del evento para procesarla.

Tipo: cadena

## parentStepID

ID de paso del paso principal del paso procesado actual en la instancia.

Tipo: cadena

## parentStepName

Nombre del paso principal del paso actual.

Tipo: cadena

## parentTransitionID

Id de la transición que ha llevado la instancia al paso procesado.

Tipo: cadena

## parentTransitionName

Nombre de la transición que ha llevado la instancia al paso procesado.

Tipo: cadena

## inTest

Se indica si este recorrido está en modo de prueba o no.

Tipo: booleano

## processingTime

Cantidad total de tiempo en milisegundos desde la entrada del paso de la instancia hasta el final del procesamiento.

Tipo: long

## instanceType

Indica el tipo de instancia, si es por lotes o unitarios.

Tipo: cadena

Valores: lote/unidad

## recurrenceIndex

Índice de la periodicidad si el recorrido es por lotes y recurrente (la primera ejecución tiene el índice de recurrencia = 1).

Tipo: long

## isBatchToUnitary

Indica si esta instancia unitaria se ha activado desde una instancia por lotes.

Tipo: booleano

## batchExternalKey

Clave externa para el evento por lotes.

Tipo: cadena

## batchInstanceID

es el ID de instancia por lotes.

Tipo: cadena

## batchUnitaryBranchID

si la instancia se ha activado desde una instancia de lote, ID de rama unitaria.

Tipo: cadena
