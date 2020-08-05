---
title: Pasos adicionales para enviar eventos al Journey Orchestration
description: Obtenga información sobre los pasos adicionales para enviar eventos al Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---



# Additional steps to send events to [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Al crear un evento, [!DNL Journey Orchestration] genera automáticamente un ID para este evento. El sistema que empuja el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. Consulte [](../event/previewing-the-payload.md).

Para configurar los eventos que se enviarán **[!UICONTROL Streaming Ingestion APIs]** y se utilizarán en [!DNL Journey Orchestration], debe seguir estos pasos:

1. Obtenga la URL de entrada de las API de Adobe Experience Platform (consulte API de [inserción de flujo](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/streaming/overview.html)).
1. Copie la carga útil de la previsualización de carga útil en el **[!UICONTROL Event]** menú. Consulte [](../event/defining-the-payload-fields.md).

A continuación, debe configurar el sistema de datos que envía eventos a las API de inserción de flujo mediante la carga útil copiada:

1. Configure una llamada de API de POST en la URL de las API de inserción de flujo (denominada entrada).
1. Utilice la carga útil que copió [!DNL Journey Orchestration] en el cuerpo (&quot;sección de datos&quot;) de la llamada de API a las API de inserción de flujo. Vea a continuación un ejemplo
1. Determine dónde obtener todas las variables presentes en la carga útil. Ejemplo: si se supone que el evento debe transmitir la dirección, la carga útil pegada mostrará &quot;dirección&quot;: &quot;string&quot;. &quot;string&quot; debe reemplazarse por la variable que rellenará automáticamente el valor correcto, el correo electrónico de la persona a la que se enviará un mensaje. Tenga en cuenta que en la previsualización de carga útil, en la **[!UICONTROL Header]** sección, rellenamos automáticamente muchos valores que se espera que faciliten su trabajo.
1. Seleccione &quot;application/json&quot; como tipo de cuerpo.
1. Pase el identificador de organización de IMS en el encabezado utilizando la clave &quot;x-gw-ims-org-id&quot;. Para el valor, utilice su identificador de organización de IMS (&quot;XXX@AdobeOrg&quot;).

A continuación se muestra un ejemplo de un evento de API de inserción de flujo:

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

Para facilitar la identificación del lugar donde pegar la parte &quot;datos&quot;, puede utilizar una herramienta de visualización JSON como [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Para solucionar problemas con las API de inserción de flujo, consulte esta [página](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/streaming/troubleshooting.html).
