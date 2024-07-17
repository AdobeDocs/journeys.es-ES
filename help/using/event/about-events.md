---
product: adobe campaign
title: Acerca de los eventos
description: Más información sobre los eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 100%

---

# Principio general {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Acerca de los eventos"
>abstract="Un evento está vinculado a una persona. Hace referencia al comportamiento de una persona o a algo que sucede vinculado a una persona. Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones."

Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de fidelidad). Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones.

Esta configuración es **obligatoria**[!DNL Journey Orchestration], ya que está diseñado para escuchar eventos y siempre la realiza un **usuario técnico**.

La configuración de eventos permite definir la información que [!DNL Journey Orchestration] recibirá como eventos. Puede utilizar varios eventos (en diferentes pasos de un recorrido) y varios recorridos pueden utilizar el mismo evento.

Si edita un evento utilizado en un recorrido en borrador o activo, solo puede cambiar el nombre, la descripción o agregar campos de carga útil. Limitamos estrictamente la edición de los recorridos en borrador o en directo para evitar que se rompan.

Puede definir dos tipos de eventos:

* Eventos basados **en reglas**: este tipo de evento no genera ningún eventID. Con el sencillo editor de expresiones simple, solo tendrá que definir una regla que el sistema utilizará para identificar los eventos relevantes que desencadenarán sus recorridos. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo, la ubicación del perfil o el número de elementos agregados al carro de compras del perfil.

  >[!CAUTION]
  >
  >Se define una regla de límite para los eventos basados en reglas. Limita el número de eventos calificados que un recorrido puede procesar a 5000 por segundo para una organización determinada (ORG). Corresponde a los SLA de Journey Orchestration. Consulte esta [página](https://helpx.adobe.com/es/legal/product-descriptions/journey-orchestration.html).

* Eventos **generados por el sistema**: estos eventos requieren un eventID. Este campo eventID se genera automáticamente al crear el evento. El sistema que impulsa el evento no debe generar un ID, debe pasar el que está disponible en la previsualización de carga útil.

Journey Orchestration requiere que los eventos se transmitan o se envíen por lotes a Adobe Experience Platform. Estos datos no necesariamente tienen que ir al perfil en tiempo real. Si desea utilizar los eventos para la segmentación o la búsqueda en un recorrido independiente, le recomendamos que habilite el conjunto de datos para el perfil.

Para aprender a crear un evento, consulte esta [página](../event/about-creating.md).
