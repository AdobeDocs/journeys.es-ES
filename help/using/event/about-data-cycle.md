---
product: adobe campaign
title: Ciclo de datos de evento
description: Descubra más información sobre el ciclo de datos de eventos
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 79%
---
# Ciclo de datos {#section_r1f_xqt_pgb}

Los eventos son llamadas API POST. Los eventos se envían a Adobe Experience Platform a través de las API de ingesta de streaming. El destino URL de los eventos enviados a través de las API de mensajería transaccional se denomina &quot;entrada&quot;. La carga útil de eventos sigue el formato XDM.

La carga útil contiene la información requerida por las API de ingesta de streaming para funcionar (en el encabezado) y la información requerida por [!DNL Journey Orchestration] para funcionar (el ID de evento, la parte del cuerpo de carga útil) y la información que se va a utilizar en los recorridos (en el cuerpo, por ejemplo, la cantidad de un carro de compras abandonado). Existen dos modos para la ingesta de streaming: autenticado y no autenticado. Para obtener más información sobre las API de ingesta de streaming, consulte [este vínculo](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=es).

Después de llegar a través de las API de ingesta de streaming, los eventos fluyen a un servicio interno llamado Canalización y, a continuación, a Adobe Experience Platform. Si el esquema de evento tiene habilitado el indicador de Servicio de Perfil del cliente en tiempo real y un ID de conjunto de datos que también tiene el indicador de Perfil del cliente en tiempo real, se desplaza al servicio de Perfil del cliente en tiempo real.

Para los eventos generados por el sistema, la canalización filtra los eventos que tienen una carga útil que contiene [!DNL Journey Orchestration] eventIDs (consulte el proceso de creación de eventos que se muestra a continuación) proporcionados por [!DNL Journey Orchestration] y contenidos en la carga útil de evento. En el caso de los eventos basados en reglas, el sistema identifica el evento con la condición eventID. Estos eventos son escuchados por [!DNL Journey Orchestration] y se activa el recorrido correspondiente.
