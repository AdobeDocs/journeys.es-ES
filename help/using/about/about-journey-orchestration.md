---
product: adobe campaign
title: Acerca de Journey Orchestration
description: Obtenga más información sobre Journey Orchestration
feature: Recorridos
role: Business Practitioner
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 100%

---

# Acerca de [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

[!DNL Journey Orchestration] es un servicio de aplicaciones integrado en Adobe Experience Platform.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] permite la orquestación en tiempo real basada en datos contextuales de eventos, información de Adobe Experience Platform o datos de servicios API de terceros. Puede configurar una acción personalizada si utiliza un sistema de terceros para enviar sus mensajes. Si tiene Adobe Campaign Standard, podrá enviar correos electrónicos, notificaciones push y SMS usando las [capacidades de mensajes transaccionales](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html) de Adobe Campaign Standard.

En la pestaña de configuración de eventos, un **usuario técnico** configura los eventos que se esperan en los recorridos. Los datos entrantes de los eventos se normalizan siguiendo el modelo de datos de Experience de Adobe (XDM). Los eventos provienen de las API de ingesta de transmisión para eventos autenticados y no autenticados (como eventos del SDK de Adobe Mobile).

En la pestaña de configuración de la fuente de datos, un **usuario técnico** configura:

* Los diferentes campos expuestos desde Adobe Experience Platform en el diseñador de recorridos con fines de acondicionamiento y personalización.
* Las fuentes de datos personalizadas adicionales que se aprovechan en el diseñador de recorridos. Las fuentes de datos personalizadas son conexiones entre sistemas o servicios de terceros y [!DNL Journey Orchestration] a través de API. Puede conectar un sistema de terceros, como un sistema de fidelidad. Los servicios de terceros pueden ser, por ejemplo, una API meteorológica.

Con el diseñador de recorridos, un **usuario empresarial** puede arrastrar y soltar fácilmente un evento de entrada, agregar condiciones y especificar la acción que se va a realizar.

A continuación, cree condiciones basadas en lo siguiente:

* tiempo
* datos procedentes de la carga útil de evento
* información procedente de fuentes de datos: fuente de datos del perfil de cliente en tiempo real o fuentes de datos personalizadas

Puede utilizar la condición de división para enviar a las personas en el recorrido a diferentes direcciones.

Mediante actividades de acción, puede enviar un mensaje a través de un sistema de terceros. Si tiene Adobe Campaign Standard, envíe mensajes de texto personalizados en tiempo real, notificaciones push o correos electrónicos.

Como [!DNL Journey Orchestration] es multipaso, puede crear escenarios avanzados. Por ejemplo, después de un primer evento y una primera acción, puede arrastrar otros eventos. A continuación, puede agregar una segunda acción, colocar una actividad de espera para esperar un tiempo, agregar una condición dividida para empujar a las personas a dos rutas diferentes y, a continuación, enviar mensajes diferentes.

>[!NOTE]
>
>Esta documentación se actualiza con frecuencia para reflejar los cambios recientes en el producto. Sin embargo, algunas capturas de pantalla pueden diferir ligeramente de la interfaz del producto.
