---
product: adobe campaign
solution: Journey Orchestration
title: Importar descripción de API de exportación
description: Obtenga más información sobre la API de exportación de importación.
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 3%

---


# Uso de Export-Import API

Exporte una versión del viaje y todos sus objetos relacionados (viaje, eventos, fuentes de datos, grupos de campos, acciones personalizadas) con una sola llamada de API. La carga útil resultante de la exportación puede utilizarse para importar fácilmente el viaje a otro entorno (instancia o zona de pruebas).
Esta función le permite administrar sus viajes en varias instancias o en varios flujos de trabajo de entornos de prueba.


## Recursos

La API de exportación e importación de Journey Orchestration se describe en un archivo Swagger disponible [aquí](https://adobedocs.github.io/JourneyAPI/docs/).

Para utilizar esta API con la instancia de Journey Orchestration, debe utilizar la consola de AdobeI/O. Puede realizar inicios siguiendo esta [Introducción a Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) y luego utilizar las secciones de esta página.

Para probar y preparar la integración, hay una colección Postman disponible [aquí](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flujo de exportación e importación

Se recomienda seguir estos pasos para exportar e importar los viajes a través de entornos:

1. Cree un viaje en el entorno de inicio y establezca parámetros para él. [Más información aquí](https://docs.adobe.com/content/help/es-ES/journeys/using/building-journeys/about-journey-building/journey.html)
1. Compruebe si la versión del viaje no tiene errores. [Más información aquí](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Llame a la API **/lista/viajes** para recuperar el viaje UID y el UID de su última versión del viaje. Si es necesario, puede llamar **/travesías/`{uid}`/última** para encontrar el UID de su última versión del viaje.
1. Llame a la API de **exportación** con los parámetros de entorno de inicio (orgID y sandboxName).
1. Abra la carga útil de devolución y, a continuación, compruebe los siguientes elementos:
   * Si el viaje exportado contiene credenciales **** específicas, debe reemplazar estas credenciales por las correspondientes al nuevo entorno.
   * Si el viaje exportado contiene **eventos** que apuntan a un esquema **** XDM, deberá actualizar manualmente la referencia de ID de esquema con el ID de esquema del nuevo entorno en el nodo xdmEntity si los valores de ID son diferentes. Esta actualización debe realizarse para cada evento. [Más información aquí](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Si el viaje contiene acciones de correo electrónico, sms o push, es posible que tenga que actualizar el nombre de la plantilla o el nombre de mobileApp si el nombre del entorno de destinatario es distinto del de su entorno de inicio.
1. Llame a la API de **importación** con los parámetros de entorno de destinatario (orgID y sandboxName). Tenga en cuenta que puede llamar a la API de importación tantas veces como desee. El UUID y el nombre de cada objeto incluido en el viaje se generan cada vez que se llama a la API de importación.
1. Una vez importado el viaje, puede publicarlo en la aplicación Journey Orchestration. Más información [aquí](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Autentificación

### Configuración del acceso a API

El acceso a la API de Journey Orchestration se configura a través de los pasos a continuación. Cada uno de estos pasos se detalla en la documentación [de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe I/O.

>[!CAUTION]
>
>Para administrar certificados en Adobe I/O, asegúrese de que tiene derechos de administrador <b></b> del sistema en la organización o una cuenta [de](https://helpx.adobe.com/enterprise/using/manage-developers.html) desarrollador en la consola de administración.

1. **Compruebe que dispone de un certificado** digital o cree uno si es necesario. Las claves pública y privada que se proporcionan con el certificado son necesarias en los pasos siguientes.
1. **Cree una nueva integración en [!DNL Journey Orchestration] Service** en Adobe I/O y configúrela. El acceso al perfil del producto es necesario para Journey Orchestration y Adobe Experience Platform. Se generarán las credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y fírmelo con su clave privada. JWT codifica toda la información de identidad y seguridad que Adobe necesita para comprobar su identidad y permitirle acceder a la API. Este paso se detalla en esta [sección](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Intercambie su JWT por un Token de acceso** a través de una solicitud de POST o a través de la interfaz de la consola de desarrollador. Este Token de acceso deberá utilizarse en cada encabezado de las solicitudes de API.

Para establecer una sesión segura de API de servicio a servicio de Adobe I/O, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la información siguiente.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZACIÓN>**: Este es su ID de organización personal, el Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;ORGANIZACIÓN> : su instancia de producción
   Para obtener el valor de ID de la organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la documentación [de](https://www.adobe.io/authentication.html)Adobe I/O).

* **&lt;ACCESS_TOKEN>**: Su token de acceso personal, que se recuperó al intercambiar su JWT a través de una solicitud de POST.

* **&lt;API_KEY>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en [!DNL Journey Orchestration] Service.



## Descripción de la API de exportación e importación

Esta API le permite exportar una versión de viaje identificada por su UID y todos los objetos relacionados (viaje, eventos, fuentes de datos, grupos de campos, acciones personalizadas) mediante su uid.
La carga útil resultante se puede utilizar para importar la versión del viaje en otro entorno (zona de pruebas o instancia).

| Método | Ruta | Descripción |
|---|---|---|
| `[POST]` | /travelVersions/import | Importar contenido de versión de viaje resultante de la exportación de una versión de viaje |
| `[GET]` | /travelVersions/`{uid}`/export | Exportación de una versión del viaje |
| `[GET]` | /journeys/`{uid}`/last | Obtenga la última versión del viaje para un viaje |
| `[POST]` | /lista/viajes | Lista de los metadatos de los viajes y sus versiones de viaje |


### Características de exportación y guardas

* El viaje debe ser válido antes de la exportación.

* Las credenciales no se exportan y se inserta un marcador de posición (es decir, INSERT_SECRET_HERE) en la carga útil de respuesta.
Después de la llamada de exportación, debe insertar manualmente las nuevas credenciales (correspondientes al entorno de destinatario) antes de importar la carga útil en el entorno de destinatario.

* Los siguientes objetos se exportan pero nunca se importarán en el entorno de destinatario. Son recursos del sistema administrados automáticamente por el Journey Orchestration. No es necesario reemplazar &quot;INSERT_SECRET_HERE&quot;.
   * **DataProviders**:  &quot;Proveedor de datos de Adobe Campaign Standard&quot; (acsDataProvider) y &quot;Experience Platform&quot; (acppsDataProvider)
   * **Grupos** de campos (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Características de importación

* Durante la importación, los objetos de viaje se crean con un nuevo UID y un nuevo nombre para garantizar la exclusividad en el entorno de destinatario (instancia o simulador de pruebas).

* Si la carga útil de importación contiene marcadores de posición secretos, se genera un error. Debe reemplazar la información de credenciales antes de la llamada del POST para importar el viaje.

## Advertencia y errores

Los posibles errores son:

* En el momento de la **exportación**, si la versión del viaje no es válida: error 500

* En el momento **de la** importación, si la carga útil no es válida tras modificaciones o si las credenciales no están bien definidas en la carga útil: error 400

* Después del paso de importación, si el ID de Esquema XDM de sus eventos no es válido en el entorno de destinatario, aparecerá un error en la aplicación Journey Orchestration. En este caso, no será posible publicar el viaje.