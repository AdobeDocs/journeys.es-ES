---
title: Additional steps to send events to Journey Orchestration
description: Learn about additional steps to send events to Journey Orchestration
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
ht-degree: 3%

---



# Additional steps to send events to [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Al crear un evento, [!DNL Journey Orchestration] genera automáticamente un ID para este evento. El sistema que empuja el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. Consulte [](../event/previewing-the-payload.md).

Para configurar los eventos que se enviarán **[!UICONTROL Streaming Ingestion APIs]** y se utilizarán en [!DNL Journey Orchestration], debe seguir estos pasos:

1. Get the inlet URL from the Adobe Experience Platform APIs (see [Streaming Ingestion APIs](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/streaming/overview.html)).
1. Copy the payload from the payload preview in the **[!UICONTROL Event]** menu. Consulte [](../event/defining-the-payload-fields.md).

You then need to configure the data system that pushes events to Streaming Ingestion APIs using the payload you copied:

1. Set up a POST API call to the Streaming Ingestion APIs URL (called an inlet).
1. Use the payload you copied from [!DNL Journey Orchestration] in the body (&quot;data section&quot;) of the API call to Streaming Ingestion APIs. See below for an example
1. Determine where to get all the variables present in the payload. Ejemplo: si se supone que el evento debe transmitir la dirección, la carga útil pegada mostrará &quot;dirección&quot;: &quot;string&quot;. &quot;string&quot; should be replaced by the variable that will automatically populate the right value, the email of the person to send a message to. Tenga en cuenta que en la previsualización de carga útil, en la **[!UICONTROL Header]** sección, rellenamos automáticamente muchos valores que se espera que faciliten su trabajo.
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

Para solucionar problemas con las API de inserción de flujo, consulte esta [página](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html).
