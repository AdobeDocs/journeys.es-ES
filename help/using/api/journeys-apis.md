---
product: adobe campaign
title: Introducción a las API de recorridos
description: Obtenga más información acerca de las API de recorridos
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 87d5cf223d9adec27eabcb55f2e09aa6d40b23a6
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 87%

---

# Introducción a las API de recorridos

## Acerca de las API de límite y limitación

Al configurar una fuente de datos o una acción, se establece una conexión con un sistema para recuperar información adicional que se utilizará en los recorridos o enviar mensajes o llamadas de API.

Las API de recorridos admiten hasta 5000 eventos por segundo, pero es posible que algunos sistemas externos o API no tengan un rendimiento equivalente. Para evitar sobrecargar estos sistemas, puede usar las API de **límite** y **limitación** para limitar el número de eventos enviados por segundo.

Cada vez que recorrido realiza una llamada a la API, esta pasa por el motor de API. Si se alcanza el límite establecido en la API, la llamada se rechaza (si utiliza la API de cierre) o se pone en cola hasta 6 horas y se procesa lo antes posible en el orden en que se recibió (si usa la API de limitación).

Por ejemplo, supongamos que ha definido una regla de límite o limitación de 100 llamadas por segundo para el sistema externo. Una acción personalizada llama al sistema en 10 recorridos diferentes. Si un recorrido recibe 200 llamadas por segundo, utilizará las 100 ranuras disponibles y descartará o pondrá en cola las 100 restantes. Como la velocidad máxima se ha superado, los otros 9 recorridos no tendrán ninguna ranura. Esta granularidad ayuda a proteger el sistema externo de sobrecargas y caídas.

>[!IMPORTANT]
>
>Las **Reglas de límite** se configuran en el nivel de zona protegida, para un extremo específico (la dirección URL denominada), pero de forma global para todos los recorridos de esa zona protegida.
>
>Las **Reglas de limitación** solo están configuradas en zonas protegidas de producción, para un extremo específico, pero de forma global para todos los recorridos de todas las zonas protegidas. Solo puede tener una configuración de limitación por organización.

Para obtener más información sobre cómo trabajar con estas API, consulte estas secciones:

* [API de límite](capping.md)
* [API de limitación](throttling.md)

Ambas API también se describen en un archivo Swagger disponible [aquí](https://adobedocs.github.io/JourneyAPI/docs/).

## Capacidad de fuentes de datos y acciones personalizadas {#capacity}

Para **fuentes de datos externas**, el número máximo de llamadas por segundo está limitado a 15. Si se supera este límite, las llamadas adicionales se descartan o se ponen en cola según la API en uso. Es posible aumentar este límite para las fuentes de datos externas privadas poniéndose en contacto con Adobe para incluir en la lista de permitidos el extremo, pero esto no es una opción para las fuentes de datos externas públicas. * [Obtenga información sobre cómo configurar fuentes de datos](../datasource/about-data-sources.md).

>[!NOTE]
>
>Si una fuente de datos utiliza una autenticación personalizada con un extremo diferente al que se usa para la fuente de datos, debe ponerse en contacto con Adobe para incluir en la lista de permitidos también este.

Para **acciones personalizadas**, debe evaluar la capacidad de su API externa. Por ejemplo, si Journey Optimizer envía 1000 llamadas por segundo y el sistema solo puede admitir 100, debe definir una configuración de límite o de limitación para que el sistema no se sature. [Obtenga información sobre cómo configurar acciones](../action/action.md)

## Configuración del acceso a API {#api}

Para usar estas API con su instancia de [!DNL Journey Orchestration], debe utilizar la consola de Adobe I/O. El acceso a la API de [!DNL Journey Orchestration] se configura mediante los pasos que siguen. Cada uno de estos pasos se detalla en la [documentación de Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para administrar certificados en Adobe I/O, asegúrese de que tiene derechos de <b>Administrador del sistema</b> sobre la organización o una [cuenta de desarrollador](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en Admin Console.

1. **Compruebe que tiene un certificado digital** o créese uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración para el servicio de [!DNL Journey Orchestration]** en Adobe I/O y configúrelo. El acceso al perfil del producto es necesario para [!DNL Journey Orchestration] y Adobe Experience Platform. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).

>[!CAUTION]
>
>El método JWT para generar tokens de acceso ha quedado obsoleto. Todas las integraciones nuevas deben crearse con el [método de autenticación de servidor a servidor OAuth](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe también recomienda migrar las integraciones existentes al método OAuth.
>
>Lea la siguiente documentación importante:
>[Guía de migración para sus aplicaciones de JWT a OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Guía de implementación para aplicaciones nuevas y antiguas con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Ventajas de utilizar el método de credenciales de servidor a servidor OAuth ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

Para establecer una sesión segura de API de Adobe I/O de servicio a servicio, cada solicitud a un servicio de Adobe debe incluir la información siguiente en el encabezado Autorización.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: este es su ID de organización personal, Adobe proporciona uno para cada una de sus instancias. Para obtener el valor del ID de organización, consulte con su administrador o contacto técnico de Adobe. También puede recuperarlo en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la [documentación de Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)).

* **&lt;ACCESS_TOKEN>**: Su token de acceso personal

* **&lt;API_KEY>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración con el servicio de [!DNL Journey Orchestration].
