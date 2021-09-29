---
title: Ejemplos de consultas
description: Ejemplos de consultas
topic: Content Management
role: User
level: Intermediate
exl-id: 07d25f8e-0065-4410-9895-ffa15d6447bb
source-git-commit: e758d4430bb28c109633c96e330b56ad08a61c02
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Ejemplos de consultas{#query-examples}

En esta sección se enumeran varios ejemplos utilizados habitualmente para consultar los eventos de los pasos de Recorrido en Data Lake.

## Errores de mensaje/acción

### Lista de cada error encontrado en los recorridos

Esta consulta le permite enumerar cada error encontrado en recorridos al ejecutar un mensaje o una acción.

_Consulta del lago de datos_

```
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName=<'message-name'>
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

_Ejemplo_

```
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName='Message - 100KB Email with Gateway and Kafkav2'
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

Esta consulta devuelve todos los errores que se han producido al ejecutar una acción en un recorrido, junto con el recuento de cuántas veces se ha producido.

## Consultas basadas en perfiles

### Buscar si un perfil entró en un Recorrido específico

_Consulta del lago de datos_

```
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Ejemplo_

```
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = 'ec9efdd0-8a7c-4d7a-a765-b2cad659fa4e' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

El resultado debe ser bueno a 0. Esta consulta devuelve el número exacto de veces que un perfil ha introducido un recorrido.

### Buscar si se envió un perfil a un mensaje específico

**Método 1:** si el nombre del mensaje no es único en el recorrido (se utiliza en varios lugares).

_Consulta del lago de datos_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='<NodeId in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Ejemplo_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='17ae65a1-02dd-439d-b54e-b56a78520eba' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

El resultado debe ser bueno a 0. Esta consulta solo nos indica si la acción del mensaje se ejecutó correctamente en el lado del recorrido.

**Método 2:** si el nombre del mensaje es único en el recorrido.

_Consulta del lago de datos_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeName='<NodeName in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_Ejemplo_

```
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='Message- 100KB Email' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

La consulta devuelve la lista de todos los mensajes junto con su recuento invocado para el perfil seleccionado.

## Buscar todos los mensajes que un perfil ha recibido en los últimos 30 días

_Consulta del lago de datos_

```
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

_Ejemplo_

```
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

La consulta devuelve la lista de todos los mensajes junto con su recuento invocado para el perfil seleccionado.

### Buscar todos los recorridos que un perfil ha introducido en los últimos 30 días

_Consulta del lago de datos_

```
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

_Ejemplo_

```
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

La consulta devuelve la lista de todos los nombres de recorrido junto con el número de veces que el perfil consultado ingresó al recorrido.

### Número de perfiles que cumplen los requisitos para un recorrido diariamente

_Consulta del lago de datos_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_Ejemplo_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

La consulta devuelve, durante el periodo definido, el número de perfiles que ingresaron al recorrido cada día. Si un perfil introducido mediante varias identidades, se contará dos veces. Si la reentrada está habilitada, el recuento de perfiles puede duplicarse en diferentes días si se vuelve a introducir el recorrido en un día diferente.

## Consultas basadas en recorridos

### Número de recorridos activos diarios

_Consulta del lago de datos_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_Ejemplo_

```
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

La consulta devuelve, durante el periodo definido, el recuento de recorridos únicos que se activan cada día. Un solo recorrido que se active en varios días se contará una vez al día.
