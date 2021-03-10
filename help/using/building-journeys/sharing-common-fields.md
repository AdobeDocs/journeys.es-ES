---
product: adobe campaign
solution: Journey Orchestration
title: campos comunes de los eventos de los recorridos
description: campos comunes de los eventos de los recorridos
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# campos comunes {#sharing-common-fields} de los eventos de los recorridos

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

Tipo: string

## nodeID

ID de nodo de cliente (desde el lienzo).

Tipo: string

## stepID

ID único del paso que se está procesando actualmente.

Tipo: string

## stepName

Nombre del paso que se está procesando actualmente.

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

Estado del paso, que representa el estado del paso, cuándo se ha completado su procesamiento (y el evento de paso se ha activado).

Tipo: string

El estado puede ser:

* finalizado: el paso no tiene transición y su procesamiento ha finalizado correctamente.
* error: el procesamiento de pasos ha generado un error.
* transiciones: el paso está esperando a que un evento pase a otro paso.
* límite: el paso ha fallado en un error de restricción, producido durante una acción o enriquecimiento.
* tiempo de espera: el paso ha fallado en un error de tiempo de espera, producido durante una acción o enriquecimiento.
* instanceTimedout: el paso ha detenido su procesamiento, ya que la instancia ha alcanzado su tiempo de espera.

## journeyID

ID del recorrido.

Tipo: string

## journeyVersionID

ID de la versión de recorrido. Este id representa la referencia de identidad al recorrido, en el caso de journeyStepEvent.

Tipo: string

## journeyVersionName

Nombre de la versión de recorrido.

Tipo: string

## journeyVersion

Versión de la versión de recorrido.

Tipo: string

## instanceID

ID interno de la instancia de recorrido.

Tipo: string

## externalKey

Clave externa extraída del evento para procesarla.

Tipo: string

## parentStepID

ID de paso del paso principal del paso procesado actual en la instancia.

Tipo: string

## parentStepName

Nombre del paso principal del paso actual.

Tipo: string

## parentTransitionID

Id de la transición que ha llevado la instancia al paso procesado.

Tipo: string

## parentTransitionName

Nombre de la transición que ha llevado la instancia al paso procesado.

Tipo: string

## inTest

Se indica si este recorrido está en modo de prueba o no.

Tipo: booleano

## processingTime

Cantidad total de tiempo en milisegundos desde la entrada del paso de la instancia hasta el final del procesamiento.

Tipo: long

## instanceType

Indica el tipo de instancia, si es por lotes o unitarios.

Tipo: string

Valores: lote/unidad

## recurrenceIndex

Índice de la periodicidad si el recorrido es por lotes y recurrente (la primera ejecución tiene el índice de recurrencia = 1).

Tipo: long

## isBatchToUnitary

Indica si esta instancia unitaria se ha activado desde una instancia por lotes.

Tipo: booleano

## batchExternalKey

Clave externa para el evento por lotes.

Tipo: string

## batchInstanceID

es el ID de instancia por lotes.

Tipo: string

## batchUnitaryBranchID

si la instancia se ha activado desde una instancia de lote, ID de rama unitaria.

Tipo: string
