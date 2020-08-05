---
title: Campos de ejecución de la acción eventos de los journeyStep
description: Campos de ejecución de la acción eventos de los journeyStep
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
source-wordcount: '320'
ht-degree: 5%

---


# Campos de ejecución de la acción eventos de los journeyStep {#sharing-execution-fields}

Esta mezcla se compartirá con los eventos travelStepEvent y travelStepProfileEvent.

Si el paso tiene una acción que procesar, esos campos se agregarán a la carga útil de evento.

## actionID

ID de la acción que se está ejecutando.

Tipo: string

## actionName

Nombre de la acción. Si no se ha establecido ningún nombre, se realizará stepName.

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
* límite
* timeout
* error

## actionExecutionErrorCode

Error de ejecución de código para acción. Presente si el error tiene un código, como uno HTTP.

Tipo: string

## actionExecutionOriginError

Se puede agotar el tiempo de espera en dos casos:

* en el primer intento se ejecuta una acción. En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se está enviando un correo electrónico y se devuelve un error HTTP 500 en el primer intento. La recuperación se reintenta, pero la duración de los dos intentos excede el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como tiempo de espera. El aspecto de la parte de acción será el siguiente:

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

* builtin
* Correo electrónico ACS
* SMS ACS
* ACS Push
* cliente
* Epsilon
* ...

Tipo: string

## deliveryJobID

Describe el Id. de trabajo de envío del viaje por lotes.

Tipo: string

## batchDeliveryID

Describe el ID de envío del viaje por lotes.

Tipo: string

## fromSegmentTrigger

Se describe si el viaje por lotes se activa a partir del segmento de Audiencia.

Tipo: booleano

## actionSchedulerCount

Recuento de solicitudes de notificación de Planificador enviadas al servicio de Planificador durante el procesamiento de pasos.

Tipo: long
