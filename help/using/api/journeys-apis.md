---
product: adobe campaign
title: Introducción a las API de recorrido
description: Obtenga más información sobre las API de recorrido
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 3%

---

# Introducción a las API de recorrido

## Acerca de las API de restricción y restricción

Al configurar una fuente de datos o una acción, se establece una conexión con un sistema para recuperar información adicional que se utilizará en los recorridos o enviar mensajes o llamadas API.

Las API de Recorrido admiten hasta 5000 eventos por segundo, pero es posible que algunos sistemas externos o API no tengan un rendimiento equivalente. Para evitar sobrecargar estos sistemas, puede usar la variable **Restricción** y **Restricción** para limitar el número de eventos enviados por segundo.

Cada vez que recorrido realiza una llamada a la API, esta pasa por el motor de API. Si se alcanza el límite establecido en la API, la llamada de se rechaza si utiliza la API de restricción o se pone en cola hasta 6 horas y se procesa lo antes posible en el orden en que se recibió si utiliza la API de restricción.

Por ejemplo, supongamos que ha definido una regla de límite o restricción de 100 llamadas por segundo para su sistema externo. Una acción personalizada llama al sistema en 10 recorridos diferentes. Si un recorrido recibe 200 llamadas por segundo, utilizará las 100 ranuras disponibles y descartará o pondrá en cola las 100 ranuras restantes. Como la velocidad máxima se ha superado, los otros 9 recorridos no tendrán ninguna ranura. Esta granularidad ayuda a proteger el sistema externo de sobrecargas y caídas.

>[!IMPORTANT]
>
>**Reglas de restricción** se configuran en el nivel de entorno limitado, para un punto final específico (la dirección URL denominada) pero global para todos los recorridos de ese entorno limitado.
>
>**Reglas de restricción** solo están configuradas en entornos limitados de producción, para un punto final específico pero globales para todos los recorridos de todos los entornos limitados. Solo puede tener una configuración de regulación por organización.

Para obtener más información sobre cómo trabajar con estas API, consulte estas secciones:

* [Captación de API](capping.md)
* [API de restricción](throttling.md)

Ambas API también se describen en un archivo Swagger disponible [here](https://adobedocs.github.io/JourneyAPI/docs/).

## Fuentes de datos y capacidad de acciones personalizadas {#capacity}

Para **fuentes de datos externas**, el número máximo de llamadas por segundo está limitado a 15. Si se supera este límite, las llamadas adicionales se descartan o se ponen en cola según la API en uso. Es posible aumentar este límite para las fuentes de datos externas privadas poniéndose en contacto con el Adobe para incluir el punto final en la lista de permitidos, pero esta no es una opción para las fuentes de datos externas públicas. * [Obtenga información sobre cómo configurar fuentes de datos](../datasource/about-data-sources.md).

>[!NOTE]
>
>Si una fuente de datos utiliza una autenticación personalizada con un extremo diferente al que se usa para la fuente de datos, debe ponerse en contacto con Adobe para incluir también ese extremo en la lista de permitidos.

Para **acciones personalizadas**, debe evaluar la capacidad de su API externa. Por ejemplo, si Journey Optimizer envía 1000 llamadas por segundo y el sistema solo puede admitir 100 llamadas por segundo, debe definir una configuración de límite o de regulación para que el sistema no se satura. [Obtenga información sobre cómo configurar acciones](../action/action.md)

## Configuración del acceso a API {#api}

Para usar estas API con su [!DNL Journey Orchestration] , debe utilizar la consola de Adobe I/O. [!DNL Journey Orchestration] El acceso a la API se configura mediante los pasos a continuación. Cada uno de estos pasos se detalla en la [documentación de Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Para administrar certificados en Adobe I/O, asegúrese de que tiene <b>Administrador del sistema</b> derechos sobre la organización o [cuenta de desarrollador](https://helpx.adobe.com/es/enterprise/using/manage-developers.html) en Admin Console.

1. **Comprobar que tiene un certificado digital** o cree uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración para [!DNL Journey Orchestration] Servicio** en Adobe I/O y configúrelo. El acceso al perfil del producto es necesario para [!DNL Journey Orchestration] y Adobe Experience Platform. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).
1. **Creación de un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y firme con la clave privada. El JWT codifica toda la información de identidad y seguridad que necesita el Adobe para comprobar su identidad y permitirle acceder a la API. Este paso se detalla en esta [sección](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Intercambiar el JWT por un token de acceso** mediante una solicitud del POST o a través de la interfaz de Developer Console. Este token de acceso debe utilizarse en cada encabezado de sus solicitudes de API.

Para establecer una sesión segura de API de Adobe I/O de servicio a servicio, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la información siguiente.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Este es su ID de organización personal, el Adobe proporciona un ID de organización para cada una de sus instancias. Para obtener el valor de ID de organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la <a href="https://www.adobe.io/authentication.html">documentación de Adobe I/O</a>).

* **&lt;access_token>**: Su token de acceso personal, que se recuperó al intercambiar su JWT a través de una solicitud del POST.

* **&lt;api_key>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración a [!DNL Journey Orchestration] Servicio.
