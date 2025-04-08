---
product: adobe campaign
title: Pasos adicionales para enviar eventos a Journey Orchestration
description: Obtenga información acerca de los pasos adicionales para enviar eventos a Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Pasos adicionales para enviar eventos a [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


>[!NOTE]
>
>Al crear un evento, [!DNL Journey Orchestration] genera automáticamente un identificador para este evento. El sistema que impulsa el evento no debe generar un ID, debe utilizar el que está disponible en la previsualización de carga útil. Consulte [esta página](../event/previewing-the-payload.md).

Para configurar los eventos que se enviarán a **[!UICONTROL Streaming Ingestion APIs]** y que se utilizarán en [!DNL Journey Orchestration], debe seguir estos pasos:

1. Obtenga la URL de entrada de las API de Adobe Experience Platform (consulte [API de ingesta de transmisión](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=es)).
1. Copie la carga útil de la previsualización de carga útil en el menú **[!UICONTROL Event]**. Consulte [esta página](../event/defining-the-payload-fields.md).

A continuación, debe configurar el sistema de datos que inserta eventos en las API de ingesta de transmisión mediante la carga útil copiada:

1. Configure una llamada de la API POST a la URL de las API de ingesta de transmisión (denominada entrada).
1. Utilice la carga que copió de [!DNL Journey Orchestration] en el cuerpo (&quot;sección de datos&quot;) de la llamada de API a las API de ingesta de transmisión. Consulte a continuación un ejemplo
1. Determine dónde obtener todas las variables presentes en la carga útil. Ejemplo: si el evento debe transmitir la dirección, la carga útil pegada mostrará &quot;dirección&quot;: &quot;cadena&quot;. &quot;cadena&quot; debe reemplazarse por la variable que rellena automáticamente el valor correcto, el correo electrónico de la persona a la que enviar un mensaje. Tenga en cuenta que en la previsualización de carga útil, en la sección **[!UICONTROL Header]**, rellenamos automáticamente muchos valores que se espera que faciliten su trabajo.
1. Seleccione &quot;application/json&quot; como tipo de cuerpo.
1. Pase su ID de organización de IMS en el encabezado con la clave &quot;x-gw-ims-org-id&quot;. Para el valor, utilice su ID de organización de IMS (&quot;XXX@AdobeOrg&quot;).

Este es un ejemplo de evento de API de ingesta de transmisión:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Para facilitar la identificación del lugar donde pegar la parte de &quot;datos&quot;, puede utilizar una herramienta de visualización JSON como [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Para solucionar problemas de las API de ingesta de transmisión, consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
