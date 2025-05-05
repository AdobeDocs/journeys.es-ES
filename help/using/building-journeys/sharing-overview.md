---
product: adobe campaign
title: Información general sobre el uso compartido de los pasos del recorrido
description: Información general sobre el uso compartido de los pasos del recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 3%

---

# Información general sobre el uso compartido de los pasos del recorrido{#sharing-overview}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


[!DNL Journey Orchestration] envía automáticamente datos de rendimiento del recorrido a Adobe Experience Platform para que se puedan combinar con otros datos con fines de análisis.

>[!NOTE]
>
>Esta función se activa de forma predeterminada en todas las instancias para eventos de pasos de recorrido. No se pueden modificar ni actualizar los esquemas y conjuntos de datos que se han creado durante el aprovisionamiento para eventos de paso. De forma predeterminada, estos esquemas y conjuntos de datos están en modo de solo lectura.

Por ejemplo, ha configurado un recorrido que envía varios correos electrónicos. Esta capacidad le permite combinar datos de [!DNL Journey Orchestration] con datos de eventos descendentes, como cuántas conversiones se produjeron, cuánta participación se produjo en el sitio web o cuántas transacciones se produjeron en el almacén. La información de recorrido se puede combinar con los datos de Adobe Experience Platform, ya sea desde otras propiedades digitales o desde propiedades sin conexión para proporcionar una vista más completa del rendimiento.

[!DNL Journey Orchestration] crea automáticamente los esquemas y flujos necesarios en conjuntos de datos para Adobe Experience Platform por cada paso que realiza un individuo en un recorrido. Un evento de paso corresponde a un individuo que se mueve de un nodo a otro en un recorrido. Por ejemplo, en un recorrido que tiene un evento, una condición y una acción, se envían tres eventos de paso a Adobe Experience Platform.

La lista de campos XDM que se pasan es completa. Algunos contienen códigos generados por el sistema y otros tienen nombres descriptivos en lenguaje natural. Algunos ejemplos son la etiqueta de la actividad de recorrido o el estado del paso: cuántas veces se ha superado el tiempo de espera de una acción o ha finalizado en error.

>[!CAUTION]
>
>Los conjuntos de datos no se pueden activar para el servicio de perfil en tiempo real. Asegúrese de que la opción **[!UICONTROL Profile]** esté desactivada.

Recorrido envía datos a medida que se producen, de forma de flujo continuo. Puede consultar estos datos mediante el servicio de consultas. Puede conectarse a Customer Journey Analytics u otras herramientas de BI para ver los datos relacionados con estos pasos.

Se crean los siguientes esquemas:

* Esquema de evento de paso de recorrido para [!DNL Journey Orchestration]: evento de paso de Recorrido vinculado a metadatos de Recorrido.
* Esquema de recorrido con campos de Recorrido para [!DNL Journey Orchestration]: metadatos de Recorrido para describir Recorridos.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Se pasan los siguientes conjuntos de datos:

* Eventos de paso de recorrido
* Recorridos

![](../assets/sharing3.png)

Las listas de campos XDM pasados a Adobe Experience Platform se detallan aquí:

* [Lista de campos de eventos de paso](../building-journeys/sharing-field-list.md)
* [Campos de eventos de paso heredados](../building-journeys/sharing-legacy-fields.md)


## Integración con Customer Recorrido Analytics{#integration-cja}

Los eventos de paso de Journey Orchestration se pueden vincular a otros conjuntos de datos en [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es). Este es un flujo de trabajo general:

* Customer Journey Analytics incorpora el conjunto de datos &quot;Evento de paso de Recorrido&quot;.
* El campo **profileID** del &quot;esquema de evento de paso de Recorrido para Journey Orchestration&quot; asociado se define como un campo de identidad. En Customer Journey Analytics, puede vincular este conjunto de datos a cualquier otro conjunto de datos que tenga el mismo valor que el identificador basado en personas.
* Si desea usar este conjunto de datos en Customer Journey Analytics para el análisis de recorrido entre canales, consulte esta [documentación](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=es).
