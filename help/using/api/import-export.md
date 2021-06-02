---
product: adobe campaign
title: Importar descripción de API de exportación
description: Obtenga más información sobre la API de exportación de importación.
products: journeys
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 3%

---


# Uso de la API Export-Import

Exporte una versión de recorrido y todos sus objetos relacionados (recorrido, eventos, fuentes de datos, grupos de campos, acciones personalizadas) con una sola llamada de API. La carga útil resultante de la exportación se puede utilizar para importar fácilmente el recorrido en otro entorno (instancia o entorno limitado).
Esta función le permite administrar sus recorridos en varias instancias o en varios flujos de trabajo de entornos de prueba.


## Recursos

La API de exportación e importación de Journey Orchestration se describe en un archivo Swagger disponible [aquí](https://adobedocs.github.io/JourneyAPI/docs/).

Para utilizar esta API con la instancia de Journey Orchestration, debe utilizar la consola de Adobe I/O. Puede empezar por seguir esta [Introducción a Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) y luego utilizar las secciones de esta página.

Para probar y preparar la integración, hay una colección Postman disponible [aquí](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flujo de exportación e importación

Se recomienda seguir estos pasos para exportar e importar los recorridos entre entornos:

1. Cree y parámetros de un recorrido en su entorno de inicio. [Más información aquí](https://docs.adobe.com/content/help/es-ES/journeys/using/building-journeys/about-journey-building/journey.html)
1. Compruebe si la versión del recorrido no tiene errores. [Más información aquí](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Llame a la API **/list/recorrido** para recuperar el recorrido de UID y el UID de su última versión de recorrido. Si es necesario, puede llamar a **/recorrido/`{uid}`/later** para encontrar el UID de su última versión de recorrido.
1. Llame a la API **export** con los parámetros de entorno de inicio (orgID y sandboxName).
1. Abra la carga útil de retorno y, a continuación, compruebe los siguientes elementos:
   * Si el recorrido exportado contiene **credenciales específicas**, debe reemplazar estas credenciales con las correspondientes al nuevo entorno.
   * Si el recorrido exportado contiene **events** que apuntan a un **esquema XDM**, debe actualizar manualmente la referencia de ID de esquema con el ID de esquema del nuevo entorno en el nodo xdmEntity si los valores de ID son diferentes. Esta actualización debe realizarse para cada evento. [Más información aquí](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Si el recorrido contiene correos electrónicos, sms o acciones push, es posible que tenga que actualizar el nombre de la plantilla o el nombre de la aplicación móvil si el nombre en el entorno de destino es diferente del del entorno de inicio.
1. Llame a la API **Import** con los parámetros de entorno de destino (orgID y sandboxName). Tenga en cuenta que puede llamar a la API de importación tantas veces como desee. El UUID y el nombre de cada objeto contenido en el recorrido se generan cada vez que se llama a la API de importación.
1. Una vez importado el Recorrido, puede publicarlo en la aplicación de Journey Orchestration. Más información [aquí](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticación

### Configuración del acceso a API

El acceso a la API de Journey Orchestration se configura siguiendo los pasos que se indican a continuación. Cada uno de estos pasos se detalla en la [documentación del Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para administrar certificados en el Adobe I/O, asegúrese de que tiene <b>derechos de administrador del sistema</b> en la organización o una [cuenta de desarrollador](https://helpx.adobe.com/enterprise/using/manage-developers.html) en Admin Console.

1. **Compruebe que tiene un certificado** digital o cree uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración a  [!DNL Journey Orchestration]** Service en Adobe I/O y configúrela. El acceso al perfil de producto es necesario para Journey Orchestration y Adobe Experience Platform. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).
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
   Para obtener el valor de ID de organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la [documentación de Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Su token de acceso personal, que se recuperó al intercambiar su JWT a través de una solicitud del POST.

* **&lt;api_key>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en el servicio [!DNL Journey Orchestration].



## Descripción de la API de exportación e importación

Esta API permite exportar una versión de recorrido identificada por su UID y todos los objetos relacionados (recorrido, eventos, fuentes de datos, grupos de campos, acciones personalizadas) por su uid.
La carga útil resultante se puede utilizar para importar la versión de recorrido en otro entorno (entorno limitado o instancia).

| Método | Ruta | Descripción |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importación de contenido de versión de recorrido resultante de una exportación de versión de recorrido |
| `[GET]` | /journeyVersions/`{uid}`/export | Exportar una versión de recorrido |
| `[GET]` | /recorridos/`{uid}`/más reciente | Obtenga la versión de recorrido más reciente para un recorrido |
| `[POST]` | /list/recorrido | Lista de metadatos de los recorridos y sus versiones de recorrido |


### Características de exportación y barreras

* El recorrido debe ser válido antes de la exportación.

* Las credenciales no se exportan y un marcador de posición (es decir, INSERT_SECRET_HERE) se inserta en la carga útil de respuesta.
Después de la llamada de exportación, debe insertar manualmente las nuevas credenciales (correspondientes al entorno de destino) antes de importar la carga útil en el entorno de destino.

* Los siguientes objetos se exportan, pero nunca se importan en el entorno de destino. Son recursos del sistema administrados automáticamente por el Journey Orchestration. No es necesario reemplazar &quot;INSERT_SECRET_HERE&quot;.
   * **Proveedores de datos**: &quot;Proveedor de datos de Adobe Campaign Standard&quot; (acsDataProvider) y &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos de campos**  (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importación

* Durante la importación, los objetos de recorrido se crean con un nuevo UID y un nuevo nombre para garantizar la exclusividad en el entorno de destino (instancia o entorno limitado).

* Si la carga útil de importación contiene marcadores de posición secretos, se genera un error. Debe reemplazar la información de credenciales antes de la llamada del POST para importar el recorrido.

## Advertencia y errores

Los posibles errores son:

* En **hora de exportación**, si la versión de recorrido no es válida: error 500

* En **hora de importación**, si la carga útil no es válida después de las modificaciones o si las credenciales no están bien definidas en la carga útil : error 400

* Después del paso de importación, si el ID de esquema XDM para los eventos no es válido en el entorno de destino, aparece un error en la aplicación de Journey Orchestration. No será posible publicar el recorrido en tal caso.