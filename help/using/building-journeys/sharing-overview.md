---
title: Información general sobre el uso compartido de los pasos del viaje
description: Información general sobre el uso compartido de los pasos del viaje
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
source-git-commit: 26246bd44407a818afba8b80513cb62da9cf6ebd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---


# Información general sobre el uso compartido de los pasos del viaje{#sharing-overview}

La orquestación de viajes envía automáticamente los datos de rendimiento del viaje a Adobe Experience Platform para que se puedan combinar con otros datos con fines de análisis.

Por ejemplo, ha configurado un viaje que envía varios correos electrónicos. Esta capacidad le permite combinar datos de orquestación de viajes con datos de eventos descendentes, como cuántas conversiones se produjeron, cuánta participación se produjo en el sitio web o cuántas transacciones se produjeron en el almacén. La información del viaje se puede combinar con los datos de la Plataforma, ya sea de otras propiedades digitales o de propiedades sin conexión, para ofrecer una vista más completa del rendimiento.

La orquestación de viajes crea automáticamente los esquemas y secuencias necesarios en conjuntos de datos a la Plataforma para cada paso que un individuo realiza en un viaje. Un evento de paso corresponde a un individuo que se mueve de un nodo a otro en un viaje. Por ejemplo, en un viaje que tiene un evento, una condición y una acción, se envían tres eventos a la Plataforma.

La lista de los campos XDM que se pasan es exhaustiva. Algunos contienen códigos generados por el sistema y otros tienen nombres descriptivos legibles por el hombre. Algunos ejemplos son la etiqueta de la actividad del viaje o el estado del paso: cuántas veces se agotó el tiempo de espera de una acción o terminó en error.

>[!CAUTION]
>
>De forma predeterminada, los conjuntos de datos no están activados para el servicio de perfil en tiempo real. Si desea un conjunto de datos en el servicio de perfil, debe activarlo (alternancia de **Perfil** ). Tenga en cuenta que un gran volumen de eventos tomará almacenamientos en su cuota. Proceda con cuidado antes de activar un conjunto de datos para perfiles
>
>![](../assets/sharing4.png)

Los viajes envían datos a medida que se producen, de forma continua. Puede consulta de estos datos mediante el servicio de Consulta. Puede conectarse a Análisis del viaje del cliente u otras herramientas de BI para vista de datos relacionados con estos pasos.

Se crean los siguientes esquemas:

* esquema de Evento de Perfil de paso de viaje para orquestación de viajes - Eventos de experiencia para los pasos realizados en un viaje junto con un mapa de identidad que se utilizará para asignar a un participante de viaje individual.
* esquema de Evento de paso de viaje para orquestación de viajes: evento de paso de viaje que está vinculado a los metadatos de viaje.
* esquema de Viaje con Campos de Viaje para Orquestación de Viaje - Metadatos de Viaje para describir Viajes.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Se pasan los siguientes conjuntos de datos:

* esquema de Evento de Perfil de paso de viaje para orquestación de viajes
* Eventos de la etapa de viaje
* Viajes

![](../assets/sharing3.png)

Las listas de los campos XDM pasados a la plataforma se detallan a continuación:

* [campos comunes de los eventos de los pasos del viaje](../building-journeys/sharing-common-fields.md)
* [Campos de ejecución de la acción eventos de la travesíaPaso](../building-journeys/sharing-execution-fields.md)
* [campos de captura de datos de eventos de travesía](../building-journeys/sharing-fetch-fields.md)
* [Campos de identidad del evento de travesíaPaso](../building-journeys/sharing-identity-fields.md)
* [campos de viaje](../building-journeys/sharing-journey-fields.md)
