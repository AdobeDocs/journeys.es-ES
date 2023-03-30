---
product: adobe campaign
title: Captación de la descripción de la API
description: Obtenga más información sobre la API de restricción.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 4%

---


# Trabajar con la API de restricción {#work}

La API de restricción le ayuda a crear, configurar y supervisar sus configuraciones de restricción.

## Captación de la descripción de la API

| Método | Ruta | Descripción |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Obtener una lista de las configuraciones de restricción de extremo |
| [!DNL POST] | /endpointConfigs | Crear una configuración de restricción de extremo |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Implementación de una configuración de restricción de extremo |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Desimplementar una configuración de restricción de extremo |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Compruebe si se puede implementar o no una configuración de límite de extremo |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Actualizar una configuración de restricción de extremo |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperar una configuración de límite de extremo |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Eliminar una configuración de restricción de extremo |

Cuando se crea o actualiza una configuración, se realiza automáticamente una comprobación para garantizar la sintaxis y la integridad de la carga útil.
Si se producen algunos problemas, la operación devuelve advertencias o errores para ayudarle a corregir la configuración.

## Configuración de extremo

Esta es la estructura básica de una configuración de extremo:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Por ejemplo:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Advertencia y errores

Cuando **canDeploy** se llama al método , el proceso valida la configuración y devuelve el estado de validación identificado por su ID único, ya sea:

```
"ok" or "error"
```

Los posibles errores son:

* **ERR_ENDPOINTCONFIG_100**: configuración de restricción: falta o la dirección url no es válida
* **ERR_ENDPOINTCONFIG_101**: configuración de restricción: url mal formada
* **ERR_ENDPOINTCONFIG_102**: configuración de restricción: url con formato incorrecto: comodín en url no permitido en host:port
* **ERR_ENDPOINTCONFIG_103**: configuración de restricción: faltan métodos HTTP
* **ERR_ENDPOINTCONFIG_104**: configuración de restricción: sin clasificación de llamada definida
* **ERR_ENDPOINTCONFIG_107**: configuración de restricción: recuento máximo de llamadas no válido (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuración de restricción: recuento máximo de llamadas no válido (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configuración de restricción: no se puede crear la configuración de extremo: carga útil no válida
* **ERR_ENDPOINTCONFIG_112**: configuración de restricción: no se puede crear la configuración de extremo: esperando una carga útil JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nombre de servicio no válido `<!--<given value>-->`: debe ser &#39;dataSource&#39; o &#39;action&#39;

La advertencia potencial es:

**ERR_ENDPOINTCONFIG_106**: configuración de restricción: conexiones HTTP máximas no definidas: sin limitación de forma predeterminada

## Casos de uso

En esta sección, encontrará los cinco casos de uso principales que puede realizar para administrar la configuración de restricción en [!DNL Journey Orchestration].

Para ayudarle en las pruebas y la configuración, hay una colección de Postman disponible [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta colección de Postman se ha configurado para compartir la colección de variables de Postman generada mediante __[Integraciones de la consola Adobe I/O](https://console.adobe.io/integrations) > Pruébelo > Descargar para Postman__, que genera un archivo de entorno de Postman con los valores de integraciones seleccionados.

Una vez descargado y cargado en Postman, debe añadir tres variables: `{JO_HOST}`,`{BASE_PATH}` y `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL de puerta de enlace
* `{BASE_PATH}` : punto de entrada para la API. El valor es &quot;/authoring&quot;
* `{SANDBOX_NAME}` : el encabezado **x-sandbox-name** (por ejemplo, &quot;prod&quot;) correspondiente al nombre del simulador de pruebas donde se realizarán las operaciones de API. Consulte la [información general sobre los entornos limitados](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) para obtener más información.

En la siguiente sección, encontrará la lista ordenada de llamadas al resto de API para realizar el caso de uso.

Caso de uso n°1: **Creación e implementación de una nueva configuración de restricción**

1. list
1. crear
1. candeploy
1. implementar

Caso de uso n°2: **Actualización e implementación de una configuración de límite aún no implementada**

1. list
1. obtener
1. actualizar
1. candeploy
1. implementar

Caso de uso n°3: **Desimplementar y eliminar una configuración de restricción implementada**

1. list
1. anular implementación
1. eliminar

Caso de uso n°4: **Elimine una configuración de restricción implementada.**

En una sola llamada de API, puede anular la implementación y eliminar la configuración con el uso del parámetro forceDelete .
1. list
1. delete, con el parámetro forceDelete

Caso de uso n°5: **Actualización de una configuración de límite ya implementada**

1. list
1. obtener
1. actualizar
1. anular implementación
1. candeploy
1. implementar
