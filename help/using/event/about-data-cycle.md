---
product: adobe campaign
solution: Journey Orchestration
title: Ciclo de datos de evento
description: Información sobre el ciclo de datos de evento
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 79%

---


# Ciclo de datos {#section_r1f_xqt_pgb}

Los eventos son llamadas API POST. Los eventos se envían a Adobe Experience Platform a través de las API de ingesta de transmisión. El destino URL de los eventos enviados a través de las API de mensajería transaccional se denomina &quot;entrada&quot;. La carga útil de eventos sigue el formato XDM.

La carga útil contiene la información requerida por las API de ingesta de transmisión para funcionar (en el encabezado) y la información requerida por [!DNL Journey Orchestration] para funcionar (el ID de evento, la parte del cuerpo de carga útil) y la información que se va a utilizar en los recorridos (en el cuerpo, por ejemplo, la cantidad de un carro de compras abandonado). Existen dos modos para la transmisión de flujo continuo: autenticado y no autenticado. Para obtener más información sobre las API de ingesta de flujos, consulte [este vínculo](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/api/getting-started.html).

Después de llegar a través de las API de ingesta de transmisión, los eventos fluyen a un servicio interno llamado Canalización y, a continuación, a Adobe Experience Platform. Si el esquema de evento tiene habilitado el indicador de Servicio de Perfil del cliente en tiempo real y un ID de conjunto de datos que también tiene el indicador de Perfil del cliente en tiempo real, se desplaza al servicio de Perfil del cliente en tiempo real.

Para los eventos generados por el sistema, los eventos de filtros de canalización que tienen una carga útil que contiene [!DNL Journey Orchestration] eventIDs (consulte el proceso de creación de eventos más abajo) proporcionados por [!DNL Journey Orchestration] y contenidos en la carga útil de evento. Para eventos basados en reglas, el sistema identifica el evento mediante la condición eventID. Estos eventos son escuchados por [!DNL Journey Orchestration] y se activa el recorrido correspondiente.
