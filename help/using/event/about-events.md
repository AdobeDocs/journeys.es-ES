---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de los eventos
description: Más información sobre los eventos
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: f73e357d8947997f7f5872efa6a5ef4f51bc63a9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 49%

---


# Principio general {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Acerca de los eventos"
>abstract="Un evento está vinculado a una persona. Se refiere al comportamiento de una persona o a algo que suceda vinculado a una persona. Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones."

Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones.

Esta configuración es **obligatoria**[!DNL Journey Orchestration], ya que está diseñado para escuchar eventos y siempre la realiza un **usuario técnico**.

La configuración de eventos permite definir la información que [!DNL Journey Orchestration] recibirá como eventos. Puede utilizar varios eventos (en diferentes pasos de un recorrido) y varios recorridos pueden utilizar el mismo evento.

Si edita un evento utilizado en un recorrido en borrador o activo, solo puede cambiar el nombre, la descripción o agregar campos de carga útil. Limitamos estrictamente la edición de los recorridos en borrador o en directo para evitar que se rompan.

Puede definir dos tipos de eventos:

* **Eventos basados** en reglas: este tipo de evento no genera un eventID. Con el editor de expresiones simple, simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que van a almacenar en déclencheur sus recorridos. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de compras del perfil.

   >[!CAUTION]
   >
   >Se define una regla de límite para los eventos basados en reglas. Limita el número de eventos calificados que un recorrido puede procesar a 5000 por segundos para una organización determinada (ORG). Corresponde a los SLA de Journey Orchestration. Consulte esta [página](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html).

* **Eventos** generados por el sistema: estos eventos requieren un eventID. Este campo eventID se genera automáticamente al crear el evento. El sistema que impulsa el evento no debe generar un ID, debe pasar el disponible en la previsualización de carga útil.

Para aprender a crear un evento, consulte esta [página](../event/about-creating.md).

