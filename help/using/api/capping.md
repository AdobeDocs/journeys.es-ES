---
title: Descripción de la API de límite
description: Obtenga más información sobre la API de límite.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9f28bdc0e74359ff9f8d84961769b84973ae3f39
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 2%

---


# Uso de la API de límite

## Introducción

Las API de Journey Orquestation admiten 5000 eventos/segundos, pero algunos sistemas externos o API no pueden tener un rendimiento equivalente. Es por eso que Journey Orquestation viene con una función dedicada llamada API de límite para monitorear y limitar la tasa que imponemos a los sistemas externos.

Durante una configuración de origen de datos, definirá una conexión a un sistema para recuperar información adicional que se utilizará en sus viajes o, para una definición de acción, configurará la conexión de un sistema de terceros para enviar mensajes o llamadas de API. Cada vez que Journey realiza una llamada de API, se consulta la API de límite y la llamada se realiza a través del motor de API. Si hay un límite definido, la llamada se rechaza y el sistema externo no se sobrecarga.

Para obtener más información sobre la acción o la configuración de orígenes de datos, consulte [Acerca de las acciones](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) o [Acerca de los orígenes de datos](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Recursos

La API de límite de orquestación de viajes se describe en un archivo Swagger disponible [aquí](https://adobedocs.github.io/JourneyAPI/docs/).

Para utilizar esta API con su instancia de orquestación de viajes, debe utilizar la consola de AdobeIO. Puede realizar inicios siguiendo esta [Introducción a Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) y, a continuación, utilizar las secciones de esta página.

Para probar y preparar la integración, hay una colección Postman disponible [aquí](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autentificación

### Configuración del acceso a API

El acceso a la API de orquestación de viajes se configura a través de los siguientes pasos. Cada uno de estos pasos se detalla en la documentación [de E/S de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!CAUTION]
>
>Para administrar certificados en la E/S de Adobe, asegúrese de que tiene derechos de administrador <b></b> del sistema en la organización o una cuenta <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">de</a> desarrollador en la consola de administración.

1. **Compruebe que dispone de un certificado** digital o cree uno si es necesario. Las claves pública y privada que se proporcionan con el certificado son necesarias en los pasos siguientes.
1. **Cree una nueva integración en el servicio** de orquestación de viajes en la E/S de Adobe y configúrela. El acceso al perfil del producto es necesario para la orquestación de viajes y la plataforma de Adobe Experience. Se generarán las credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y fírmelo con su clave privada. JWT codifica toda la información de identidad y seguridad que Adobe necesita para verificar su identidad y permitirle acceder a la API. Este paso se detalla en esta [sección](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Intercambie su JWT por un Token de acceso** a través de una solicitud POST o a través de la interfaz de la consola de desarrollador. Este Token de acceso deberá utilizarse en cada encabezado de las solicitudes de API.

Para establecer una sesión segura de la API de Adobe I/O servicio a servicio, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la información siguiente.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZACIÓN>**: Este es su ID de organización personal; Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;ORGANIZACIÓN> : su instancia de producción
   Para obtener el valor de ID de organización, consulte a su administrador o al contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la documentación <a href="https://www.adobe.io/authentication.html">de E/S de</a>Adobe).

* **&lt;ACCESS_TOKEN>**: Su token de acceso personal, que se recuperó al intercambiar su JWT a través de una solicitud POST.

* **&lt;API_KEY>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en el servicio de orquestación de viajes.



## Descripción de la API de límite

La API de límite le ayuda a crear, configurar y supervisar sus configuraciones de límite.

| Método | Ruta | Descripción |
|---|---|---|
| POST | lista/valores extremosConfiguraciones | Obtener una lista de las configuraciones de límite de extremo |
| POST | /endConfigs | Crear una configuración de límite de extremo |
| POST | /endConfigs/{uid}/deploy | Implementar una configuración de límite de extremo |
| POST | /endConfigs/{uid}/undeploy | Desimplementar una configuración de límite de extremo |
| POST | /endConfigs/{uid}/canDeploy | Compruebe si se puede implementar o no una configuración de límite de extremo |
| PUT | /endConfigs/{uid} | Actualizar una configuración de límite de extremo |
| OBTENER | /endConfigs/{uid} | Recuperar una configuración de límite de extremo |
| ELIMINAR | /endConfigs/{uid} | Eliminar una configuración de límite de puntos |

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

### Ejemplo:

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

Cuando se llama a un método **canDeploy** , el proceso valida la configuración y devuelve el estado de validación identificado por su ID única, ya sea:

```
"ok" or "error"
```

Los posibles errores son:

* **ERR_ENDPOINTCONFIG_100**: capping config: dirección URL que falta o no es válida
* **ERR_ENDPOINTCONFIG_101**: capping config: url mal formada
* **ERR_ENDPOINTCONFIG_102**: capping config: url incorrecta: comodín en dirección URL no permitido en host:puerto
* **ERR_ENDPOINTCONFIG_103**: capping config: faltan métodos HTTP
* **ERR_ENDPOINTCONFIG_104**: capping config: sin clasificación de llamada definida
* **ERR_ENDPOINTCONFIG_107**: capping config: recuento máximo de llamadas no válido (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: recuento máximo de llamadas no válido (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: capping config: no se puede crear la configuración del extremo: carga útil no válida
* **ERR_ENDPOINTCONFIG_112**: capping config: no se puede crear la configuración del extremo: esperando una carga útil JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nombre de servicio no válido <!--<given value>-->: debe ser &#39;dataSource&#39; o &#39;action&#39;


La advertencia potencial es:

**ERR_ENDPOINTCONFIG_106**: capping config: conexiones HTTP máximas no definidas: sin limitación de forma predeterminada



## Casos de uso

En esta sección, encontrará los cinco casos de uso principales que puede realizar para administrar la configuración de topping en Orquestación de Viaje.

Para ayudarle en las pruebas y la configuración, [aquí](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)encontrará una colección Postman.

Esta colección Postman se ha configurado para compartir la colección Variable Postman generada a través de las integraciones __[de la consola de](https://console.adobe.io/integrations)Adobe I/O > Pruébelo > Descargar para Postman__, que genera un archivo Entorno Postman con los valores de integraciones seleccionados.

Una vez descargado y cargado en Postman, debe agregar dos variables: `{JO_HOST}` y `{Base_Path}`.
* `{JO_HOST}` :: URL de puerta de enlace de orquestación de viajes
* `{BASE_PATH}` :: punto de entrada para la API. El valor es &#39;/authoring&#39;



Caso de uso n°1: **Creación e implementación de una nueva configuración de límite**

1. lista
1. crear
1. canimplementar
1. implementar

Caso de uso n°2: **Actualizar e implementar una configuración de límite aún no implementada**

1. lista
1. get
1. update
1. canimplementar
1. implementar

Caso de uso n° 3: **Desimplementar y eliminar una configuración de límite implementada**

1. lista
1. anular implementación
1. delete

Caso de uso n°4: **Elimine una configuración de límite implementada.**

En una sola llamada de API, puede anular la implementación y eliminar la configuración con el uso del parámetro forceDelete.
1. lista
1. delete, con parámetro forceDelete

Caso de uso n°5: **Actualización de una configuración de límite ya implementada**

1. lista
1. get
1. update
1. anular implementación
1. canimplementar
1. implementar
