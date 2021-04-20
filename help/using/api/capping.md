---
product: adobe campaign
solution: Journey Orchestration
title: Captación de la descripción de la API
description: Obtenga más información sobre la API de restricción.
products: journeys
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 2%

---


# Uso de la API de restricción

## Introducción

[!DNL Journey Orchestration]Las API de admiten 5000 eventos/segundos, pero algunos sistemas externos o API no podían tener un rendimiento equivalente. Por eso [!DNL Journey Orchestration] viene con una función dedicada llamada API de restricción para monitorizar y limitar la tasa que imponemos a los sistemas externos.

Durante una configuración de fuente de datos, definirá una conexión con un sistema para recuperar información adicional que se utilizará en sus recorridos o, para una definición de acción, configurará la conexión de un sistema de terceros para enviar mensajes o llamadas API. Cada vez que un Recorrido realiza una llamada a la API, se consulta la API de límite y la llamada se realiza a través del motor de API. Si hay un límite definido, la llamada se rechaza y el sistema externo no se sobrecarga.

Para obtener más información sobre la acción o la configuración de orígenes de datos, consulte [Acerca de las acciones](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) o [Acerca de las fuentes de datos](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Recursos

>[!NOTE]
>
>La API de límite [!DNL Journey Orchestration] se describe dentro de un archivo Swagger disponible [aquí](https://adobedocs.github.io/JourneyAPI/docs/).

Para utilizar esta API con su instancia [!DNL Journey Orchestration], debe utilizar la consola de Adobe I/O. Puede empezar por seguir esta [Introducción a Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) y luego utilizar las secciones de esta página.

Para probar y preparar la integración, hay una colección Postman disponible [aquí](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autenticación

### Configuración del acceso a API

[!DNL Journey Orchestration] El acceso a la API se configura mediante los pasos a continuación. Cada uno de estos pasos se detalla en la [documentación del Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para administrar certificados en el Adobe I/O, asegúrese de que tiene <b>derechos de administrador del sistema</b> en la organización o una [cuenta de desarrollador](https://helpx.adobe.com/enterprise/using/manage-developers.html) en Admin Console.

1. **Compruebe que tiene un certificado** digital o cree uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración a  [!DNL Journey Orchestration]** Service en Adobe I/O y configúrela. El acceso al perfil de producto es necesario para [!DNL Journey Orchestration] y Adobe Experience Platform. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)**  a partir de las credenciales generadas anteriormente y firme con su clave privada. El JWT codifica toda la información de identidad y seguridad que necesita el Adobe para comprobar su identidad y permitirle acceder a la API. Este paso se detalla en esta [sección](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Intercambie el JWT por un token de acceso** a través de una solicitud del POST o a través de la interfaz de Developer Console. Este token de acceso debe utilizarse en cada encabezado de sus solicitudes de API.

Para establecer una sesión de API de Adobe I/O de servicio a servicio segura, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la siguiente información.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Este es su ID de organización personal, el Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;organization> : su instancia de producción

   Para obtener el valor de ID de organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la <a href="https://www.adobe.io/authentication.html">documentación de Adobe I/O</a>).

* **&lt;access_token>**: Su token de acceso personal, que se recuperó al intercambiar su JWT a través de una solicitud del POST.

* **&lt;api_key>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en el servicio [!DNL Journey Orchestration].



## Captación de la descripción de la API

La API de restricción le ayuda a crear, configurar y supervisar sus configuraciones de restricción.

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

Cuando se llama a un método **canDeploy** , el proceso valida la configuración y devuelve el estado de validación identificado por su ID único, ya sea:

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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nombre de servicio no válido  `<!--<given value>-->`: debe ser &#39;dataSource&#39; o &#39;action&#39;


La advertencia potencial es:

**ERR_ENDPOINTCONFIG_106**: configuración de restricción: conexiones HTTP máximas no definidas: sin limitación de forma predeterminada



## Casos de uso

En esta sección, encontrará los cinco casos de uso principales que puede realizar para administrar la configuración de restricción en [!DNL Journey Orchestration].

Para ayudarle en las pruebas y la configuración, hay una colección Postman disponible [aquí](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Esta colección Postman se ha configurado para compartir la colección Variable Postman generada a través de __[Integraciones de la Consola de Adobe I/O](https://console.adobe.io/integrations) > Probar > Descargar para Postman__, que genera un archivo Entorno Postman con los valores de integraciones seleccionados.

Una vez descargado y cargado en Postman, debe añadir tres variables: `{JO_HOST}`,`{Base_Path}` y `{SANDBOX_NAME}`.
* `{JO_HOST}` :  [!DNL Journey Orchestration] URL de puerta de enlace
* `{BASE_PATH}` : punto de entrada para la API. El valor es &quot;/authoring&quot;
* `{SANDBOX_NAME}` : el encabezado  **x-sandbox-name**  (por ejemplo, &quot;prod&quot;) correspondiente al nombre del simulador para pruebas donde se realizarán las operaciones de API. Consulte la [información general de los entornos limitados](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) para obtener más información.

En la siguiente sección, encontrará la lista ordenada de llamadas al resto de API para realizar el caso de uso.

Caso de uso n°1: **Creación e implementación de una nueva configuración de límite**

1. lista
1. crear
1. candeploy
1. implementar

Caso de uso n°2: **Actualice e implemente una configuración de límite que aún no esté implementada**

1. lista
1. get
1. actualizar
1. candeploy
1. implementar

Caso de uso n°3: **Anule la implementación y elimine una configuración de restricción implementada**

1. lista
1. anular implementación
1. delete

Caso de uso n°4: **Elimine una configuración de restricción implementada.**

En una sola llamada de API, puede anular la implementación y eliminar la configuración con el uso del parámetro forceDelete .
1. lista
1. delete, con el parámetro forceDelete

Caso de uso n°5: **Actualizar una configuración de límite ya implementada**

1. lista
1. get
1. actualizar
1. anular implementación
1. candeploy
1. implementar

