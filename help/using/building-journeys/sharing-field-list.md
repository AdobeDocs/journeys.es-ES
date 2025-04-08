---
title: Lista de campos de eventos de paso
description: Lista de campos de eventos de paso
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 16%

---

# Lista de campos de eventos de paso {#sharing-field-list}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


Los campos de eventos de paso están organizados por categoría.

* Campos de información de depuración
* Campos del recorrido
* Campos de perfil
* Campos de evento de servicio

## debugInfo

| Nombre del campo | Tipo | Descripción |
|---|---|------------|
| requestId | Cadena | El ID de solicitud utilizado por Journey Orchestration para rastrear el flujo de una solicitud. |

## recorrido

Este grupo de campos se utiliza en el esquema de recorrido (en relación con journeyStepEvent). Contiene los siguientes campos:

| Nombre del campo | Tipo | Descripción |
|---|---|------------|
| ID | Cadena | Identificador del Recorrido determinado |
| VersionID | Cadena | ID de la versión del recorrido. Este ID representa la identidad de un recorrido |
| name | Cadena | Nombre del recorrido |
| descripción | Cadena | Descripción del recorrido |
| version | Cadena | versión, representada como `major`.`minor` |

## perfil

Este grupo de campos es específico de journeyStepEvent: este evento está relacionado con el recorrido y no tiene el identityMap, que describe la identidad del perfil, si la hay.

Para journeyStepEvent, también es necesario añadir campos relacionados con la identidad:

| Nombre del campo | Tipo | Descripción |
|---|---|------------|
| ID | Cadena | El identificador de perfil identifica el perfil enviado/utilizado en un recorrido. Por ejemplo: foo@adobe.com. |
| namespace | Cadena | En este campo se describe el área de nombres a la que hace referencia el perfil utilizado en el Recorrido. Por ejemplo: correo electrónico, ECID |

## serviceEvents

Este mixin contiene todos los campos correspondientes a un trabajo de exportación de perfiles.

| Nombre del campo | Tipo | Descripción |
|---|---|------------|
| ID | Cadena | El identificador del trabajo de exportación de segmentos activado |
| estado | Cadena | El estado del trabajo de exportación de segmentos: en cola, iniciado, finalizado |
| exportCountTotal | Entero | El valor máximo posible del trabajo de exportación de segmentos |
| exportCountRealized | Entero | El número real de segmentos exportados a través del trabajo |
| exportCountFailed | Entero | El número de segmentos que fallaron al exportar a través del trabajo |
| exportSegmentID | Cadena | El identificador del segmento que se exporta |
| eventType | Cadena | El tipo de evento que indica si es un evento de error del evento de información: Información, Error |
| eventCode | Cadena | El código de error que indica el motivo del eventType correspondiente |

## stepEvents

Esta categoría contiene los campos de eventos de paso originales. Consulte esta [sección](../building-journeys/sharing-legacy-fields.md).
