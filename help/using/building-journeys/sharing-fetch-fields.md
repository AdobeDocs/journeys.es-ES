---
product: adobe campaign
solution: Journey Orchestration
title: Campos de captura de datos de eventos del journeyStep
description: Campos de captura de datos de eventos del journeyStep
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 4%

---


# Campos de captura de datos de eventos del journeyStep {#sharing-fetch-fields}

Esta mezcla la compartirán journeyStepEvent y journeyStepProfileEvent.

Durante el procesamiento de un paso, es posible que no se recuperen datos en grupos de campos.

## fetchTotalTime

Cantidad total de tiempo empleado en la recuperación de datos en millones durante el procesamiento del paso.

Tipo: long

## fetchTypeInError

Define si la recuperación por error se realiza en Adobe Experience Platform o en una fuente de datos personalizada.

Tipo: string

Valores:
* aep
* custom

## fetchError

Tipo de error que se produce cuando se procesa la captura de datos.

Tipo: string

Valores:
* http
* restricción
* timedout
* error

## fetchErrorCode

Código de error de recuperación. Presente si el error tiene un código, como uno HTTP. Por ejemplo, si actionExecError es http, el código 404 representa el error HTTP 404.

Tipo: string

## fetchOriginError

Puede producirse un tiempo de espera, en dos casos:

* en el primer intento, se ejecuta la acción . En este caso, la ejecución no ha finalizado, por lo que no hay ningún error subyacente
* en un reintento: en este caso, actionExecOrigError/actionExecOrigErrorCode describe el error encontrado en el intento antes del reintento.

Por ejemplo, se están recuperando datos del servicio de perfil unificado y se devuelve un error HTTP 500 en el primer intento. Se vuelve a intentar la recuperación, pero la duración de los 2 intentos supera el tiempo de espera. A continuación, la ejecución de la acción se etiqueta como tiempo de espera. La parte de acción tendrá el siguiente aspecto:

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

El código de error proporcionado por el sistema [!DNL Journey Orchestration] está consultando. Por ejemplo, puede ser 404, 500, etc.

Tipo: string

## fetchCount

Cuántas veces se recuperan los datos, independientemente del tipo de origen.

Tipo: long

## fetchPlatformTotalTime

Cantidad total de tiempo que se tardó en recuperar los datos de Adobe Experience Platform en millones. Comentario: esta cantidad de tiempo se calcula desde el momento en que el motor envía el evento de enriquecimiento al servicio de enriquecimiento y recibe la respuesta.

Tipo: long

## fetchPlatformCount

Cuántas veces se recuperan los datos de Adobe Experience Platform.

Tipo: long

## fetchCustomTotalTime

Cantidad de tiempo para recuperar los datos personalizados en milisegundos. Comentario: esta cantidad de tiempo se calcula desde el momento en que el motor envía el evento de enriquecimiento al servicio de enriquecimiento y recibe la respuesta

Tipo: long

## fetchCustomCount

Cuántas veces se obtienen los datos personalizados de sistemas externos.

Tipo: long
