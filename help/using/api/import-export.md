---
product: adobe campaign
title: Importar descripción de API de exportación
description: Obtenga más información sobre la API de exportación de importación.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 2%

---


# Uso de la API Export-Import

Exporte una versión de recorrido y todos sus objetos relacionados (recorrido, eventos, fuentes de datos, grupos de campos, acciones personalizadas) con una sola llamada de API. La carga útil resultante de la exportación se puede utilizar para importar fácilmente el recorrido en otro entorno (instancia o entorno limitado).
Esta función le permite administrar sus recorridos en varias instancias o en varios flujos de trabajo de entornos de prueba.


## Recursos

La API de exportación e importación de Journey Orchestration se describe en un archivo Swagger disponible [here](https://adobedocs.github.io/JourneyAPI/docs/).

Para utilizar esta API con la instancia de Journey Orchestration, debe utilizar la consola de Adobe I/O. Puede empezar por seguir esta [Introducción a Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) y, a continuación, utilice las secciones de esta página.

Para probar y preparar la integración, hay disponible una colección Postman [here](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flujo de exportación e importación

Se recomienda seguir estos pasos para exportar e importar los recorridos entre entornos:

1. Cree y parámetros de un recorrido en su entorno de inicio. [Más información aquí](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Compruebe si la versión del recorrido no tiene errores. [Más información aquí](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. La llamada **/list/recorrido** para recuperar el recorrido de UID y el UID de su última versión de recorrido. Si es necesario, puede llamar a **/recorridos/`{uid}`/última** para encontrar el UID de su última versión de recorrido.
1. Llame a la función **exportar** con los parámetros de entorno de inicio (orgID y sandboxName).
1. Abra la carga útil de retorno y, a continuación, compruebe los siguientes elementos:
   * Si el recorrido exportado contiene **credenciales específicas**, debe reemplazar estas credenciales con las correspondientes al nuevo entorno.
   * Si el recorrido exportado contiene **events** que apuntan a un **Esquema XDM**, debe actualizar manualmente la referencia de ID de esquema con el ID de esquema del nuevo entorno en el nodo xdmEntity si los valores de ID son diferentes. Esta actualización debe realizarse para cada evento. [Más información aquí](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Si el recorrido contiene correos electrónicos, sms o acciones push, es posible que tenga que actualizar el nombre de la plantilla o el nombre de la aplicación móvil si el nombre en el entorno de destino es diferente del del entorno de inicio.
1. Llame a la función **Importar** API con los parámetros de entorno de destino (orgID y sandboxName). Tenga en cuenta que puede llamar a la API de importación tantas veces como desee. El UUID y el nombre de cada objeto contenido en el recorrido se generan cada vez que se llama a la API de importación.
1. Una vez importado el Recorrido, puede publicarlo en la aplicación de Journey Orchestration. Más información [here](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticación

### Configuración del acceso a API

El acceso a la API de Journey Orchestration se configura siguiendo los pasos que se indican a continuación. Cada uno de estos pasos se detalla en la [documentación de Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para administrar certificados en Adobe I/O, asegúrese de que tiene <b>Administrador del sistema</b> derechos sobre la organización o [cuenta de desarrollador](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en Admin Console.

1. **Comprobar que tiene un certificado digital** o cree uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración para [!DNL Journey Orchestration] Servicio** en Adobe I/O y configúrelo. El acceso al perfil de producto es necesario para Journey Orchestration y Adobe Experience Platform. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).
1. **Creación de un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y firme con la clave privada. El JWT codifica toda la información de identidad y seguridad que necesita el Adobe para comprobar su identidad y permitirle acceder a la API. Este paso se detalla en esta [sección](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Intercambiar el JWT por un token de acceso** mediante una solicitud del POST o a través de la interfaz de Developer Console. Este token de acceso debe utilizarse en cada encabezado de sus solicitudes de API.

Para establecer una sesión segura de API de Adobe I/O de servicio a servicio, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la información siguiente.

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

* **&lt;api_key>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración a [!DNL Journey Orchestration] Servicio.



## Descripción de la API de exportación e importación

Esta API permite exportar una versión de recorrido identificada por su UID y todos los objetos relacionados (recorrido, eventos, fuentes de datos, grupos de campos, acciones personalizadas) por su uid.
La carga útil resultante se puede utilizar para importar la versión de recorrido en otro entorno (entorno limitado o instancia).

| Método | Ruta | Descripción |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importación de contenido de versión de recorrido resultante de una exportación de versión de recorrido |
| `[GET]` | /journeyVersions/`{uid}`/export | Exportar una versión de recorrido |
| `[GET]` | /recorridos/`{uid}`/última | Obtenga la versión de recorrido más reciente para un recorrido |
| `[POST]` | /list/recorrido | Lista de metadatos de los recorridos y sus versiones de recorrido |


### Características de exportación y barreras

* El recorrido debe ser válido antes de la exportación.

* Las credenciales no se exportan y un marcador de posición (es decir, INSERT_SECRET_HERE) se inserta en la carga útil de respuesta.
Después de la llamada de exportación, debe insertar manualmente las nuevas credenciales (correspondientes al entorno de destino) antes de importar la carga útil en el entorno de destino.

* Los siguientes objetos se exportan, pero nunca se importan en el entorno de destino. Son recursos del sistema administrados automáticamente por el Journey Orchestration. No es necesario reemplazar &quot;INSERT_SECRET_HERE&quot;.
   * **Proveedores de datos**: &quot;Proveedor de datos de Adobe Campaign Standard&quot; (acsDataProvider) y &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos de campo** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importación

* Durante la importación, los objetos de recorrido se crean con un nuevo UID y un nuevo nombre para garantizar la exclusividad en el entorno de destino (instancia o entorno limitado).

* Si la carga útil de importación contiene marcadores de posición secretos, se genera un error. Debe reemplazar la información de credenciales antes de la llamada del POST para importar el recorrido.

## Advertencia y errores

Los posibles errores son:

* At **tiempo de exportación**, si la versión de recorrido no es válida : error 500

* At **tiempo de importación**, si la carga útil no es válida después de las modificaciones o si las credenciales no están bien definidas en la carga útil : error 400

* Después del paso de importación, si el ID de esquema XDM para los eventos no es válido en el entorno de destino, aparece un error en la aplicación de Journey Orchestration. No será posible publicar el recorrido en tal caso.