---
product: adobe campaign
title: campos comunes de eventos de recorridos
description: campos comunes de eventos de recorridos
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# campos comunes de eventos de recorridos {#sharing-common-fields}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


Este mixin lo compartirán journeyStepEvent y journeyStepProfileEvent.

Estos son los campos XDM comunes que [!DNL Journey Orchestration] envía a Adobe Experience Platform. Se envían campos comunes para cada paso que se procesa en un recorrido. Se utilizan campos más específicos para acciones personalizadas y enriquecimientos.

Algunos de estos campos solo están disponibles en patrones de procesamiento específicos (ejecución de acciones, recuperación de datos, etc.) para limitar el tamaño de los eventos.

## entrada

Indica si el usuario ha introducido el recorrido. Si no está presente, suponemos que el valor es falso.

Tipo: booleano

Valores: true/false

## reentrada

Indica si el usuario ha vuelto a entrar en el recorrido con la misma instancia. Si no está presente, suponemos que el valor es falso.

Tipo: booleano

Valores: true/false

## instanceEnded

Indica si la instancia ha finalizado (correctamente o no).

Tipo: booleano

## eventID

ID de evento en procesamiento, para el procesamiento de pasos. Si el evento es externo, el valor es su eventId. Si el evento es interno, el valor es el eventId interno (como scheduledNotificationReceived, executeAction, etc.).

Tipo: cadena

## nodeID

ID del nodo del cliente (desde el lienzo).

Tipo: cadena

## stepID

ID único del paso que se está procesando actualmente.

Tipo: cadena

## stepName

Nombre de la etapa que se está procesando actualmente.

Tipo: cadena

## stepType

Tipo de paso.

Tipo: cadena

Valores posibles:

* Condición
* Acción
* Planificador
* Temporizador

## stepStatus

Estado del paso, que representa el estado del paso, cuando se ha realizado su procesamiento (y se ha activado el evento del paso).

Tipo: cadena

El estado puede ser el siguiente:

* ended: el paso no tiene transición y su procesamiento ha finalizado correctamente.
* error: el procesamiento de pasos ha producido un error.
* transiciones: el paso está esperando un evento para pasar a otro paso.
* límite: el paso ha fallado debido a un error de límite, producido durante una acción o enriquecimiento.
* timeout: el paso ha fallado en un error de timeout, producido durante una acción o enriquecimiento.
* instanceTimedout: el paso ha detenido su procesamiento porque la instancia ha alcanzado su tiempo de espera.

## journeyID

ID del recorrido.

Tipo: cadena

## journeyVersionID

ID de la versión del recorrido. Este ID representa la referencia de identidad al recorrido, en el caso de journeyStepEvent.

Tipo: cadena

## journeyVersionName

Nombre de la versión del recorrido.

Tipo: cadena

## journeyVersion

Versión de la versión del recorrido.

Tipo: cadena

## instanceID

ID interno de la instancia de recorrido.

Tipo: cadena

## externalKey

Clave externa extraída del evento para procesarlo.

Tipo: cadena

## parentStepID

ID del paso principal del paso procesado actual en la instancia.

Tipo: cadena

## parentStepName

Nombre del paso principal del paso actual.

Tipo: cadena

## parentTransitionID

ID de la transición que ha llevado la instancia al paso procesado.

Tipo: cadena

## parentTransitionName

Nombre de la transición que ha llevado la instancia al paso procesado.

Tipo: cadena

## inTest

Se indica si este recorrido está en modo de prueba o no.

Tipo: booleano

## processingTime

Cantidad total de tiempo en milisegundos desde la entrada del paso de instancia hasta el final del procesamiento.

Tipo: long

## instanceType

Indica el tipo de instancia, si es por lotes o unitario.

Tipo: cadena

Valores: lote/unitario

## recurrenceIndex

Índice de periodicidad si el recorrido es por lotes y recurrente (la primera ejecución tiene recurrenceIndex = 1).

Tipo: long

## isBatchToUnitary

Indica si esta instancia unitaria se ha activado desde una instancia de lote.

Tipo: booleano

## batchExternalKey

Clave externa del evento por lotes.

Tipo: cadena

## batchInstanceID

este es el ID de instancia de lote.

Tipo: cadena

## batchUnitaryBranchID

si la instancia se ha activado desde una instancia de lote, ID de rama unitario.

Tipo: cadena
