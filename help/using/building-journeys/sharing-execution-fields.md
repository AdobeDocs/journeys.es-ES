---
product: adobe campaign
title: Campos de ejecución de la acción de eventos de journeySteps
description: Campos de ejecución de la acción de eventos de journeySteps
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 14%

---

# Campos de ejecución de la acción de eventos de journeySteps {#sharing-execution-fields}

Este mixin lo compartirán journeyStepEvent y journeyStepProfileEvent.

Si el paso tiene una acción que procesar, esos campos se añadirán a la carga útil de evento.

## actionID

ID de la acción que se está ejecutando.

Tipo: cadena

## actionName

Nombre de la acción. Si no se ha definido ningún nombre, se tomará el stepName.

Tipo: cadena

## actionType

Tipo de acción.

Tipo: cadena

## actionParameterized

Indica si la acción está parametrizada o no.

Tipo: booleano

## actionExecutionTime

Cantidad de tiempo (en milisegundos) que se tarda en ejecutar una acción actual.

Tipo: long

## actionExecutionError

Tipo de error que se produce cuando se llama a la acción.

Tipo: cadena

Valores:
* http
* límite
* timeout
* error

## actionExecutionErrorCode

Código para error de ejecución de acción. Está presente si el error tiene un código, como uno HTTP.

Tipo: cadena

## actionExecutionOriginError

Se puede producir un tiempo de espera en dos casos:

* en el primer intento se ejecuta una acción. En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se envía un correo electrónico y se devuelve un error HTTP 500 en el primer intento. Se vuelve a intentar realizar la recuperación, pero la duración de los dos intentos supera el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como timeout. La parte de acción tendrá este aspecto:

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

Tipo: cadena

## actionExecutionOriginCode

Código de error de actionExecOrigError.

Tipo: cadena

## actionBusinessType

Indica el tipo de acción.

Valores:

* integrado
* Correo electrónico ACS
* ACS SMS
* Push de ACS
* cliente
* Épsilon
* ...

Tipo: cadena

## deliveryJobID

Se describe el ID de trabajo de envío para el Recorrido por lotes.

Tipo: cadena

## batchDeliveryID

Describe la ID de envío del Recorrido por lotes.

Tipo: cadena

## fromSegmentTrigger

Describe si el Recorrido por lotes se activa desde el segmento de audiencia.

Tipo: booleano

## actionSchedulerCount

Recuento de solicitudes de notificación del planificador enviadas al servicio del planificador durante el procesamiento del paso.

Tipo: long
