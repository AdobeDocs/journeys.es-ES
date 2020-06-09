---
title: Acerca de Journey Orchestration
description: Obtenga más información sobre Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 19%

---


# Acerca de [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

[!DNL Journey Orchestration] es un servicio de aplicaciones integrado con la plataforma de experiencias.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] permite la orquestación en tiempo real basada en datos contextuales de eventos, información de Adobe Experience Platform o datos de servicios API de terceros. Puede configurar una acción personalizada si utiliza un sistema de terceros para enviar sus mensajes. Si dispone de Adobe Campaign Standard, podrá enviar correos electrónicos, notificaciones push y SMS mediante las funciones de mensajería [transaccional de Adobe Campaign Standard](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

En la ficha Configuración de evento, un usuario **** técnico configura los eventos que se esperan en los viajes. Los datos entrantes de los eventos se normalizan siguiendo el modelo de datos de experiencia de Adobe (XDM). Los Eventos provienen de las API de inserción de flujo para eventos autenticados y no autenticados (como eventos del SDK de Adobe Mobile).

En la ficha de configuración del origen de datos, un usuario **** técnico configura:

* The different fields exposed from the Adobe Experience Platform in the journey designer for condition building and personalization purposes.
* Las fuentes de datos personalizadas adicionales que se aprovechan en el diseñador de viajes. Las fuentes de datos personalizadas son conexiones entre sistemas [!DNL Journey Orchestration] y servicios de terceros a través de API. Puede conectar un sistema de terceros, como un sistema de fidelidad. Los servicios de terceros pueden ser, por ejemplo, una API meteorológica.

Con el diseñador de viajes, un usuario **de** negocios puede arrastrar y soltar fácilmente un evento de entrada, agregar condiciones y especificar la acción que se va a realizar.

A continuación, cree condiciones basadas en:

* time
* datos procedentes de la carga útil de evento
* información procedente de fuentes de datos: Origen de datos de Perfil del cliente en tiempo real o fuentes de datos personalizadas

Puede utilizar la condición de división para enviar a las personas en el viaje a diferentes direcciones.

Mediante actividades de acción, puede enviar un mensaje a través de un sistema de terceros. Si tiene Adobe Campaign Standard, envíe mensajes de texto personalizados en tiempo real, notificaciones push o correos electrónicos.

As [!DNL Journey Orchestration] is multistep, you can create advanced scenarios. Por ejemplo, después de un primer evento y una primera acción, puede arrastrar otros eventos. A continuación, puede agregar una segunda acción, colocar una actividad de espera para esperar un tiempo, agregar una condición dividida para empujar a las personas a dos rutas diferentes y, a continuación, enviar mensajes diferentes.

>[!NOTE]
>
>Esta documentación se actualiza con frecuencia para reflejar los cambios recientes en el producto. Sin embargo, algunas capturas de pantalla pueden diferir ligeramente de la interfaz del producto.
