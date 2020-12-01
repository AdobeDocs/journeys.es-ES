---
product: adobe campaign
solution: Journey Orchestration
title: Acerca de los eventos
description: Más información sobre eventos
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 54%

---


# Principio general {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Acerca de los eventos"
>abstract="Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones."

Un evento está vinculado a una persona. Se refiere al comportamiento de una persona (por ejemplo, una persona compró un producto, visitó una tienda, salió de un sitio web, etc.) o algo que suceda vinculado a una persona (por ejemplo, una persona alcanzó 10 000 puntos de lealtad). Esto es lo que escucha [!DNL Journey Orchestration] en los recorridos para orquestar las mejores próximas acciones.

Esta configuración es **obligatoria**[!DNL Journey Orchestration], ya que está diseñado para escuchar eventos y siempre la realiza un **usuario técnico**.

La configuración de eventos permite definir la información que [!DNL Journey Orchestration] recibirá como eventos. Puede utilizar varios eventos (en diferentes pasos de un recorrido) y varios recorridos pueden utilizar el mismo evento.

Si edita un evento utilizado en un recorrido en borrador o activo, solo puede cambiar el nombre, la descripción o agregar campos de carga útil. Limitamos estrictamente la edición de los recorridos en borrador o en directo para evitar que se rompan.

Puede definir dos tipos de eventos:

* **Eventos basados** en reglas: este tipo de evento no genera un eventID. Con el simple editor de expresiones, simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que activarán sus viajes. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de perfiles.

   >[!CAUTION]
   >
   >Se define una regla de límite para eventos basados en reglas. Limita el número de eventos cualificados que un viaje puede procesar a 400 k por minuto. Para obtener más información, póngase en contacto con el punto de contacto del programa Alfa. Además de esta regla de límite, se define un límite de 5000 eventos para segundos en el nivel de viaje.

* **Eventos generados** por el sistema: estos eventos requieren un eventID. Este campo eventID se genera automáticamente al crear el evento. El sistema que empuja el evento no debe generar un ID, debe pasar el disponible en la previsualización de carga útil.

Para obtener información sobre cómo crear un evento, consulte esta [página](../event/about-creating.md).

