---
product: adobe campaign
title: Campos de captura de datos de eventos de journeySteps
description: Campos de captura de datos de eventos de journeySteps
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 7%

---

# Campos de captura de datos de eventos de journeySteps {#sharing-fetch-fields}

Este mixin lo compartirán journeyStepEvent y journeyStepProfileEvent.

Durante el procesamiento de un paso, es posible que no se recuperen datos en los grupos de campos.

## fetchTotalTime

Cantidad total de tiempo invertido en la captura de datos en milisegundos durante el procesamiento del paso.

Tipo: long

## fetchTypeInError

Define si el error de recuperación se produce en Adobe Experience Platform o en un origen de datos personalizado.

Tipo: cadena

Valores:
* aep
* personalizado

## fetchError

Tipo de error que se produce cuando se procesa la captura de datos.

Tipo: cadena

Valores:
* http
* límite
* timeout
* error

## fetchErrorCode

Código para error de recuperación. Está presente si el error tiene un código, como uno HTTP. Por ejemplo, si actionExecError es http, el código 404 representa el error HTTP 404.

Tipo: cadena

## fetchOriginError

Se puede producir un tiempo de espera en dos casos:

* en el primer intento, se ejecuta la acción. En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se están recuperando datos del servicio de perfil unificado y se devuelve un error HTTP 500 en el primer intento. Se vuelve a intentar realizar la recuperación, pero la duración de los dos intentos supera el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como timeout. La parte de acción tendrá este aspecto:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: cadena

## fetchOriginErrorCode

El código de error proporcionado por el sistema [!DNL Journey Orchestration] está consultando. Por ejemplo, puede ser un 404, 500, etc.

Tipo: cadena

## fetchCount

La cantidad de veces que se recuperan los datos, independientemente del tipo de origen.

Tipo: long

## fetchPlatformTotalTime

Cantidad total de tiempo que se tarda en recuperar los datos de Adobe Experience Platform en milisegundos. Observación: esta cantidad de tiempo se calcula desde el momento en que el motor envía el evento de enriquecimiento al servicio de enriquecimiento y recibe la respuesta.

Tipo: long

## fetchPlatformCount

La cantidad de veces que se recuperan los datos de Adobe Experience Platform.

Tipo: long

## fetchCustomTotalTime

Cantidad de tiempo para recuperar los datos personalizados en milisegundos. Observación: esta cantidad de tiempo se calcula desde el momento en que el motor envía el evento de enriquecimiento al servicio de enriquecimiento y recibe la respuesta

Tipo: long

## fetchCustomCount

Cantidad de veces que se recuperan los datos personalizados de sistemas externos.

Tipo: long
