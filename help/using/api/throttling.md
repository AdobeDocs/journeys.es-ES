---
product: adobe campaign
title: Trabajar con la API de restricción
description: Obtenga más información sobre la API de restricción
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 3%

---

# Trabajar con la API de restricción

La API de restricción le ayuda a crear, configurar y supervisar sus configuraciones de restricción.

>[!IMPORTANT]
>
>Actualmente solo se permite una configuración por organización. Se debe definir una configuración en un entorno limitado de producción (se proporciona mediante x-sandbox-name en los encabezados).
>
>Se aplica una configuración a nivel de organización.
>
>Cuando se alcanza el límite establecido en la API, se ponen en cola otros eventos durante un máximo de 6 horas. Este valor no se puede modificar.

## Descripción de la API de restricción {#description}

| Método | Ruta | Descripción |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Obtener una lista de las configuraciones de regulación |
| [!DNL POST] | /throttlingConfigs | Crear una configuración de restricción |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Implementar una configuración de restricción |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Desimplementar una configuración de restricción |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Compruebe si una configuración de restricción se puede implementar o no |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Actualizar una configuración de restricción |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Recuperar una configuración de restricción |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Eliminar una configuración de restricción |

## Configuración de restricción {#configuration}

Esta es la estructura de una configuración de regulación. **name** y **descripción** los atributos son opcionales.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Por ejemplo:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Errores

Al crear o actualizar una configuración, el proceso valida la configuración dada y devuelve el estado de validación identificado por su ID único, ya sea:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Los atributos **maxThroughput**, **urlPattern** y **métodos** son obligatorios.
>
>**maxThroughput** debe estar en el rango 200-5000.

Al crear, eliminar o implementar la configuración de restricción, pueden producirse los siguientes errores:

* **ERR_THROTTLING_CONFIG_100**: configuración de restricción: `<mandatory attribute>` obligatorio
* **ERR_THROTTLING_CONFIG_101**: configuración de restricción: maxThroughput es necesario y debe ser bueno o igual a 200 y menor o igual que 5000
* **ERR_THROTTLING_CONFIG_104**: configuración de restricción: patrón de url incorrecto
* **ERR_THROTTLING_CONFIG_105**: configuración de restricción: no se permiten comodines en la parte host del patrón de url
* **ERR_THROTTLING_CONFIG_106**: configuración de restricción: carga útil no válida
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, &quot;No se puede eliminar una configuración de restricción implementada. Desimplementarlo antes de eliminarlo&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;No se puede eliminar la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;No se puede implementar la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;No se puede anular la implementación de la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;No se puede obtener la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;No se puede actualizar la configuración de restricción: la versión de tiempo de ejecución no está activa&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;No se puede actualizar la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Operación no permitida en la configuración de regulación: simulador de pruebas sin producción&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;No se puede crear la configuración de restricción: se produce un error inesperado&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;No se puede crear la configuración de restricción: solo se permite una configuración por organización&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, &quot;No se puede implementar la configuración de restricción: ya implementado&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, &quot;configuración de restricción no encontrada&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, &quot;No se puede anular la implementación de la configuración de restricción: aún no implementado&quot;

**Ejemplos de errores**

Al intentar crear una configuración en un entorno limitado que no sea de prod:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

En caso de que el sanbox dado no exista:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Al intentar crear otra configuración:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Casos de uso {#uc}

Para ayudarle en las pruebas y la configuración, hay una colección de Postman disponible [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

Esta colección de Postman se ha configurado para compartir la colección de variables de Postman generada mediante __[Integraciones de la consola Adobe I/O](https://console.adobe.io/integrations) > Pruébelo > Descargar para Postman__, que genera un archivo de entorno de Postman con los valores de integraciones seleccionados.

Una vez descargado y cargado en Postman, debe añadir tres variables: `{JO_HOST}`,`{BASE_PATH}` y `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL de puerta de enlace
* `{BASE_PATH}` : punto de entrada para la API. El valor es &quot;/authoring&quot;
* `{SANDBOX_NAME}` : el encabezado **x-sandbox-name** (por ejemplo, &quot;prod&quot;) correspondiente al nombre del simulador de pruebas donde se realizarán las operaciones de API. Consulte la [información general sobre los entornos limitados](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es) para obtener más información.

En la siguiente sección, encontrará la lista ordenada de llamadas al resto de API para realizar el caso de uso.

Caso de uso n°1: **Creación e implementación de una nueva configuración de regulación**

1. list
1. crear
1. candeploy
1. implementar

Caso de uso n°2: **Actualizar e implementar una configuración de restricción aún no implementada**

1. list
1. obtener
1. actualizar
1. candeploy
1. implementar

Caso de uso n°3: **Desimplementar y eliminar una configuración de restricción implementada**

1. list
1. anular implementación
1. eliminar

Caso de uso n°4: **Eliminar una configuración de restricción implementada**

En una sola llamada de API, puede anular la implementación y eliminar la configuración con el uso del parámetro forceDelete .

1. list
1. delete, con el parámetro forceDelete

Caso de uso n°5: **Actualizar una configuración de restricción ya implementada**

>[!NOTE]
>
>No es necesario anular la implementación de la configuración antes de actualizar

1. list
1. obtener
1. actualizar

## Ciclo de vida de configuración a nivel de tiempo de ejecución {#config}

Cuando una configuración no se implementa, se marca como inactiva en el nivel de tiempo de ejecución y los eventos pendientes se siguen procesando durante 24 horas. A continuación, se elimina en el servicio de tiempo de ejecución.

Una vez que se ha desimplementado una configuración, es posible actualizarla y volver a implementarla. Esto creará una nueva configuración de tiempo de ejecución que se tendrá en cuenta en la próxima ejecución de acciones.

Al actualizar una configuración ya implementada, los nuevos valores se tienen en cuenta inmediatamente. Los recursos del sistema subyacentes se adaptan automáticamente. Esto es óptimo comparado con anular la implementación y volver a implementar la configuración.

## Ejemplos de respuestas {#responses}

**Creación - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Actualización: PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Leer (después de la actualización): GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Leer (después de la implementación): GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```