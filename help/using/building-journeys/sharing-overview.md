---
title: Información general sobre el uso compartido de los pasos del recorrido
description: Información general sobre el uso compartido de los pasos del recorrido
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: c7a4d67af88827dfc852a281a7877efb2853facf
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# Información general sobre el uso compartido de los pasos del recorrido{#sharing-overview}

[!DNL Journey Orchestration] envía automáticamente datos de rendimiento del viaje al Adobe Experience Platform para que se puedan combinar con otros datos con fines de análisis.

>[!NOTE]
>
>Esta función no se activa de forma predeterminada en todas las instancias recientemente implementadas. La activación está a petición.

Por ejemplo, ha configurado un viaje que envía varios correos electrónicos. Esta capacidad le permite combinar [!DNL Journey Orchestration] datos con datos de eventos descendentes, como cuántas conversiones se produjeron, cuánta participación se produjo en el sitio web o cuántas transacciones se produjeron en el almacén. La información del viaje se puede combinar con los datos del Adobe Experience Platform, ya sea de otras propiedades digitales o de propiedades sin conexión, para ofrecer una vista más completa del rendimiento.

[!DNL Journey Orchestration] crea automáticamente los esquemas y flujos necesarios en conjuntos de datos para el Adobe Experience Platform para cada paso que un individuo realiza en un viaje. Un evento de paso corresponde a un individuo que se mueve de un nodo a otro en un viaje. Por ejemplo, en un viaje que tiene un evento, una condición y una acción, se envían tres eventos a Adobe Experience Platform.

La lista de los campos XDM que se pasan es exhaustiva. Algunos contienen códigos generados por el sistema y otros tienen nombres descriptivos legibles por el hombre. Algunos ejemplos son la etiqueta de la actividad del viaje o el estado del paso: cuántas veces se agotó el tiempo de espera de una acción o terminó en error.

>[!CAUTION]
>
>Los conjuntos de datos no se pueden activar para el servicio de perfil en tiempo real. Asegúrese de que la **[!UICONTROL Profile]** opción está desactivada.

Los viajes envían datos a medida que se producen, de forma continua. Puede consulta de estos datos mediante el servicio de Consulta. Puede conectarse a Customer Journey Analytics u otras herramientas de BI para vista de datos relacionados con estos pasos.

Se crean los siguientes esquemas:

* Esquema de Evento de Perfil de la etapa de viaje para [!DNL Journey Orchestration] - Eventos de experiencia para los pasos realizados en un viaje junto con un mapa de identidad que se utilizará para asignar a un participante de viaje individual.
* Esquema de Evento de paso de viaje para [!DNL Journey Orchestration] : evento de paso de viaje que está vinculado a los metadatos de viaje.
* Esquema de Viaje con Campos de Viaje para [!DNL Journey Orchestration] - Metadatos de Viaje para describir Viajes.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Se pasan los siguientes conjuntos de datos:

* Esquema de Evento del Perfil de la etapa de viaje para [!DNL Journey Orchestration]
* Eventos de la etapa de viaje
* Viajes

![](../assets/sharing3.png)

Las listas de los campos XDM pasados al Adobe Experience Platform se detallan a continuación:

* [Campos comunes de los eventos de los journeyStep](../building-journeys/sharing-common-fields.md)
* [Campos de ejecución de la acción eventos de los journeyStep](../building-journeys/sharing-execution-fields.md)
* [Campos de captura de datos de eventos del journeyStep](../building-journeys/sharing-fetch-fields.md)
* [Campos de identidad de los eventos de los journeyStep](../building-journeys/sharing-identity-fields.md)
* [campos del recorrido](../building-journeys/sharing-journey-fields.md)

Para obtener más información sobre el sistema de informes de eventos de paso a Adobe Experience Platform, vea este [tutorial en vídeo](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
