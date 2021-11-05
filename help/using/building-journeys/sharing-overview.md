---
product: adobe campaign
title: Información general sobre el uso compartido de los pasos del recorrido
description: Información general sobre el uso compartido de los pasos del recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: b557e94076bc7ce5c212246ddf313248ca10dd60
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Información general sobre el uso compartido de los pasos del recorrido{#sharing-overview}

[!DNL Journey Orchestration] envía automáticamente los datos de rendimiento del recorrido a Adobe Experience Platform para que se puedan combinar con otros datos con fines de análisis.

>[!NOTE]
>
>Esta función está activada de forma predeterminada en todas las instancias para eventos de pasos de recorrido. Para los eventos de paso del perfil de recorrido, la activación se realiza previa solicitud. No se pueden modificar ni actualizar los esquemas y conjuntos de datos que se han creado durante el aprovisionamiento de eventos de paso. De forma predeterminada, estos esquemas y conjuntos de datos están en modo de solo lectura.

Por ejemplo, ha configurado un recorrido que envía varios correos electrónicos. Esta capacidad le permite combinar [!DNL Journey Orchestration] datos con datos de evento descendente como cuántas conversiones se produjeron, cuánta participación se produjo en el sitio web o cuántas transacciones se produjeron en la tienda. La información de recorrido se puede combinar con los datos de Adobe Experience Platform, ya sea de otras propiedades digitales o de propiedades sin conexión, para ofrecer una vista más completa del rendimiento.

[!DNL Journey Orchestration] crea automáticamente los esquemas y transmisiones necesarios en conjuntos de datos a Adobe Experience Platform para cada paso que un individuo realiza en un recorrido. Un evento de paso corresponde a un individuo que se mueve de un nodo a otro en un recorrido. Por ejemplo, en un recorrido que tiene un evento, una condición y una acción, se envían tres eventos a Adobe Experience Platform.

La lista de campos XDM que se pasan es completa. Algunos contienen códigos generados por el sistema y otros tienen nombres descriptivos legibles. Algunos ejemplos son la etiqueta de la actividad de recorrido o el estado del paso: cuántas veces se agotó el tiempo de espera de una acción o finalizó con un error.

>[!CAUTION]
>
>Los conjuntos de datos no se pueden activar para el servicio de perfil en tiempo real. Asegúrese de que la variable **[!UICONTROL Profile]** la opción está desactivada.

Recorrido envía los datos a medida que se producen de forma continua. Puede consultar estos datos mediante el servicio de consulta. Puede conectarse a Customer Journey Analytics u otras herramientas de BI para ver los datos relacionados con estos pasos.

Se crean los siguientes esquemas:

* Esquema de evento de perfil de paso de recorrido para [!DNL Journey Orchestration] - Eventos de experiencia para los pasos realizados en un Recorrido junto con un mapa de identidad que se utilizará para la asignación a un participante de Recorrido individual.
* Esquema de evento de paso de recorrido para [!DNL Journey Orchestration] : evento de paso de Recorrido vinculado a metadatos de Recorrido.
* esquema de recorrido con campos de Recorrido para [!DNL Journey Orchestration] - Metadatos del Recorrido para describir los Recorridos.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Se pasan los siguientes conjuntos de datos:

* Esquema de evento de perfil de paso de recorrido para [!DNL Journey Orchestration]
* Eventos de los pasos del recorrido
* Recorridos

![](../assets/sharing3.png)

Las listas de campos XDM pasados a Adobe Experience Platform se detallan aquí:

* [Lista de campos de eventos de paso](../building-journeys/sharing-field-list.md)
* [Campos de eventos de paso heredados](../building-journeys/sharing-legacy-fields.md)

Para obtener más información sobre los eventos de paso que generan informes a Adobe Experience Platform, consulte esta [videotutorial](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
