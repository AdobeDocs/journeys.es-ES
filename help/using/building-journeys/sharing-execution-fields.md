---
product: adobe campaign
solution: Journey Orchestration
title: Campos de ejecución de la acción eventos de los journeyStep
description: Campos de ejecución de la acción eventos de los journeyStep
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 5%

---


# Campos de ejecución de la acción eventos de los journeyStep {#sharing-execution-fields}

Esta mezcla la compartirán journeyStepEvent y journeyStepProfileEvent.

Si el paso tiene que procesarse una acción, esos campos se añaden a la carga útil de evento.

## actionID

ID de la acción que se está ejecutando.

Tipo: string

## actionName

Nombre de la acción. Si no se ha establecido ningún nombre, se tomará el valor stepName.

Tipo: string

## actionType

Tipo de acción.

Tipo: string

## actionParameterized

Indica si la acción está parametrizada o no.

Tipo: booleano

## actionExecutionTime

Cantidad de tiempo (en milisegundos) que se tarda en ejecutar una acción actual.

Tipo: long

## actionExecutionError

Tipo de error que se produce cuando se llama a la acción.

Tipo: string

Valores:
* http
* restricción
* timeout
* error

## actionExecutionErrorCode

Código de error de ejecución de acción. Presente si el error tiene un código, como uno HTTP.

Tipo: string

## actionExecutionOriginError

Puede producirse un tiempo de espera, en dos casos:

* en el primer intento se ejecuta una acción. En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se envía un correo electrónico y se devuelve un error HTTP 500 en el primer intento. Se vuelve a intentar la recuperación, pero la duración de los 2 intentos supera el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como tiempo de espera. La parte de acción tendrá el siguiente aspecto:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Tipo: string

## actionExecutionOriginCode

Código de error de actionExecOrigError.

Tipo: string

## actionBusinessType

Indica el tipo de acción.

Valores:

* creación
* Correo electrónico ACS
* SMS ACS
* ACS Push
* cliente
* Epsilon
* ...

Tipo: string

## deliveryJobID

Esto describe el Id. de trabajo de entrega para el Recorrido por lotes.

Tipo: string

## batchDeliveryID

Esto describe el ID de entrega del Recorrido por lotes.

Tipo: string

## fromSegmentTrigger

Esto indica si el Recorrido de lotes se activa desde el segmento de audiencia.

Tipo: booleano

## actionSchedulerCount

Recuento de solicitudes de notificación del planificador enviadas al servicio del planificador durante el procesamiento de pasos.

Tipo: long
