---
title: Métricas y dimensiones
description: Obtenga información sobre las dimensiones y métricas disponibles para la orquestación de viajes
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Métricas y dimensiones {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Los datos de envío solo se rellenarán si tiene Adobe Campaign Standard.

Aquí puede encontrar la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.

La tabla siguiente le proporciona la lista de dimensiones utilizadas en los informes de viaje y sus definiciones.

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensiones del viaje {#MBE_table_wk4_bnj_w2b}

La tabla siguiente le proporciona la lista de dimensiones utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Dimensiones | Definición |
|--- |--- |
| **Acción** | Lista de todas las acciones (nombre de **acción - etiqueta** de acción) utilizadas en los viajes, por ejemplo: push - confirmación de salida, correo electrónico - fidelidad de las recompensas. |
| **Fuente de datos** | Lista de fuentes de datos (nombre **de fuente de** datos) utilizadas para enriquecer datos en un viaje, por ejemplo, plataforma de experiencia, sistema de reservación. |
| **[!UICONTROL Event]** | Lista de todos los eventos (nombre del **evento - etiqueta** del evento) que se utilizan en los viajes, por ejemplo: evento Geometrixx - salida de Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (nombre **del grupo de** campos) utilizados para enriquecer datos en viajes, por ejemplo, grupo de campos de perfil, sistema de reservas de Geometrixx. |
| **Viaje** | Lista de cada viaje (nombre **del** viaje) en modo de prueba y activo, por ejemplo, abandono del carro de compras, notificación de reserva del hotel. |
| **Versión de viaje** | Lista de todas las versiones publicadas de un viaje (nombre del **viaje + número** de versión), por ejemplo: abandono del carro v1, notificación de reserva del hotel v2. |
| **Orquestación** | Lista de todas las actividades de orquestación (**Condición, Fin, Espera**) definidas y utilizadas en los viajes. |

## Dimensiones de envío {#delivery-dimensions}

La tabla siguiente le proporciona la lista de dimensiones de entrega utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Dimensión | Definición |
|--- |--- |
| **Explorador** | Explorador desde el que se abrió o en el que se hizo clic en el mensaje. |
| **Nombre de envío** | Etiqueta e ID de la entrega. |
| **Dispositivo** | Dispositivo desde el cual se abrió/visualizó/hizo clic la notificación por correo electrónico/SMS/push. |
| **Tipo de mensaje** | Canal utilizado para la entrega, como correo electrónico, SMS, notificaciones push o In-App. |
| **Nombre de la aplicación móvil** | Nombre de la aplicación móvil |
| **Plataforma** | Plataforma del dispositivo desde el que se abrió/visualizó/hizo clic en el mensaje. |
| **[!UICONTROL Push platform]** | Plataforma del dispositivo desde el que se abrió la notificación push, como iOS o Android. |
| **Dominio del destinatario** | Dominio utilizado para abrir el correo electrónico. |
| **URL de seguimiento** | Dirección URL en la que el usuario hizo clic desde el mensaje. |
| **Categoría de dirección URL de seguimiento** | Categoría asignada a la dirección URL de seguimiento. |
| **Etiqueta de URL de seguimiento** | Etiqueta dada a la dirección URL, como la página espejo, póngase en contacto con nosotros o abra. |
| **Variante** | Variante del correo electrónico en caso de prueba A/B. |


## Métricas de viajes {#MBE_p_p22_c4j_w2b}

La tabla siguiente le proporciona la lista de métricas utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |---|
| **Completado** | Número total de individuos que finalizaron normalmente el viaje. |
| **Tasa de finalización** | El número total de personas que finalizaron normalmente el viaje, en comparación con el número total de personas que entraron en él. |
| **Actual** | Número total de individuos que se encuentran en el viaje, es decir, cuántas personas entraron menos las que salieron, errores y tiempo de espera agotado. |
| **Tasa actual** | El número total de personas que se encuentran en el viaje en comparación con el número de personas que han entrado en el viaje. |
| **Introducido** | Número total de eventos que se produjeron para iniciar una entrada individual en el viaje. |
| **Error** | Número total de errores que se produjeron durante un viaje pero que no impidieron que el viaje fuera exitoso. |
| **Error en la acción** | Número total de errores que se produjeron en las acciones. |
| **Error en enriquecimiento** | Número total de errores que se produjeron para un enriquecimiento de datos al llamar a un grupo de campo o fuente de datos. |
| **Error en el evento** | Número total de errores que se produjeron en los eventos. |
| **Tasa de error** | Número total de errores que se produjeron durante un viaje en comparación con el número total de ocurrencias en el mismo. |
| **Acción ejecutada** | Número total de acciones ejecutadas para un viaje. |
| **Enriquecimiento ejecutado** | Número total de enriquecimientos ejecutados llamando a un origen de datos para obtener grupos de campo específicos. |
| **Evento ejecutado** | Número total de acciones ejecutadas para un viaje. |
| **Orquestación ejecutada** | Número total de objetos de orquestación (fin, espera, condición) ejecutados para un viaje. |
| **Error** | Número total de viajes que no se ejecutaron correctamente. |
| **Tasa de error** | Número total de viajes que no se ejecutaron correctamente en comparación con el número de viajes de ejecución. |

## Métricas de envío {#delivery-metrics}

La tabla siguiente le proporciona la lista de métricas utilizadas en los informes de periodicidad, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |--- |
| **Bloqueado** | Número de destinatarios que declararon un correo electrónico como correo no deseado o no deseado. |
| **Tarifa bloqueada** | Número total de mensajes marcados como bloqueados en comparación con los mensajes enviados. |
| **Devoluciones + errores** | Total de errores acumulados durante la entrega y el procesamiento de devolución automático en relación con el número total de mensajes enviados. |
| **Devoluciones + tasa de error** | Número total de mensajes devueltos en comparación con los mensajes enviados. |
| **Haga clic** | Cantidad de veces que se hizo clic en un contenido en una entrega. |
| **Tasa de pulsaciones** | Número total de clics en una entrega en comparación con el número de mensajes enviados. |
| **Enviado** | Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados. |
| **Tasa de entrega** | Número total de mensajes enviados correctamente en comparación con los mensajes enviados. |
| **Error** | Número total de errores que se produjeron durante un viaje pero que no impidieron que el viaje fuera exitoso. |
| **Rebotes duros** | Número total de errores permanentes, como una dirección de correo electrónico incorrecta. |
| **Tasa de salida hacia otro sitio** | Número total de entregas que fallaron debido a errores permanentes en comparación con los mensajes enviados. |
| **Página de reflejo** | Número de destinatarios que hicieron clic en el vínculo de la página de reflejo. |
| **Reflejar tasa de página** | Número total de clics en el vínculo de la página de reflejo en comparación con el total de mensajes enviados. |
| **Apertura** | Número de veces que se abrió un mensaje en una entrega. |
| **Tasa de apertura** | Número total de mensajes abiertos en comparación con el número de mensajes entregados. |
| **Cuarentena** | Número de mensajes que se rebotaron y dieron como resultado la cuarentena de la dirección. |
| **Tasa de cuarentena** | Número total de cuarentena en comparación con los mensajes enviados. |
| **Rechazado** | Número de mensajes clasificados como correo no deseado por los servidores SMTP. |
| **Tasa rechazada** | Número total de mensajes marcados como rechazados en comparación con los mensajes enviados. |
| **Procesado/enviado** | Número total de envíos para la entrega. |
| **Rebote suave** | Número total de errores temporales, como una bandeja de entrada completa. |
| **Tasa de salida hacia otro sitio suave** | Número total de entregas que fallaron por un motivo temporal en comparación con los mensajes enviados. |
| **Clics únicos** | Número de destinatarios que hicieron clic en un contenido de una entrega. |
| **Aperturas únicas** | Número de destinatarios que abrieron el envío. |
| **No suscrito** | Número de clics en el vínculo de baja de suscripción. |
| **Tasa de cancelación de suscripción** | Número total de suscripciones por destinatario en comparación con los mensajes enviados. |
