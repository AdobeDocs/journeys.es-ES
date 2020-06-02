---
title: campos de captura de datos de eventos de travesía
description: campos de captura de datos de eventos de travesía
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
source-wordcount: '368'
ht-degree: 0%

---


# campos de captura de datos de eventos de travesía {#sharing-fetch-fields}

Esta mezcla se compartirá con los eventos travelStepEvent y travelStepProfileEvent.

Durante el procesamiento de un paso, se puede obtener N en los grupos de campos.

## fetchTotalTime

La cantidad total de tiempo empleado en la captura de datos en millones durante el procesamiento del paso.

Tipo: long

## fetchTypeInError

Define si el error de recuperación se encuentra en la plataforma o en un origen de datos personalizado.

Tipo: string

Valores:
* aep
* personalizado

## fetchError

Tipo de error que se produce cuando se procesa la captura de datos.

Tipo: string

Valores:
* http
* límite
* timedout
* error

## fetchErrorCode

Código de error de captura. Presente si el error tiene un código, como uno HTTP. Por ejemplo, si actionExecError es http, el código 404 representa el error HTTP 404.

Tipo: string

## fetchOriginError

Se puede agotar el tiempo de espera en dos casos:

* en el primer intento se ejecuta la acción. En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se están recuperando datos del servicio de Perfil unificado y se devuelve un error HTTP 500 en el primer intento. La recuperación se reintenta, pero la duración de los dos intentos excede el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como tiempo de espera. The action part will look like:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: string

## fetchOriginErrorCode

The Error code provided by the system Journey Orchestration is querying. For example it can be a 404, 500, etc.

Tipo: string

## fetchCount

How many times the data is fetched, regardless of the type of source.

Tipo: long

## fetchPlatformTotalTime

Cantidad total de tiempo que se tarda en recuperar los datos de la plataforma de datos en millones. Remark: this amount of time is computed from the time the engine sends the enrichment event to the enrichment service and receives the response.

Tipo: long

## fetchPlatformCount

Cuántas veces se obtienen los datos desde Plataforma.

Tipo: long

## fetchCustomTotalTime

Cantidad de tiempo para recuperar los datos personalizados en milisegundos. Comentario: esta cantidad de tiempo se calcula a partir del momento en que el motor envía el evento de enriquecimiento al servicio de enriquecimiento y recibe la respuesta

Tipo: long

## fetchCustomCount

La cantidad de veces que los datos personalizados se recuperan de sistemas externos.

Tipo: long
