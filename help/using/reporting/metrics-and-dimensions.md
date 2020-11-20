---
product: adobe campaign
solution: Journey Orchestration
title: Métricas y dimensiones
description: Obtenga información sobre las dimensiones y métricas disponibles para Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 2%

---


# Métricas y dimensiones {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Los datos de envío solo se rellenarán si tiene Adobe Campaign Standard.

Aquí puede encontrar la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.

La tabla siguiente le proporciona la lista de las dimensiones utilizadas en los informes de viaje y sus definiciones.

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensiones del viaje {#MBE_table_wk4_bnj_w2b}

La tabla siguiente le proporciona la lista de las dimensiones utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Dimension | Definición |
|--- |--- |
| **Acción** | Lista de cada acción (nombre de la **acción - etiqueta** de acción) utilizada en los viajes, por ejemplo: push - confirmación de salida, correo electrónico - fidelidad de las recompensas. |
| **Fuente de datos** | Lista de fuentes de datos (nombre **de fuente de** datos) utilizadas para enriquecer datos en un viaje, por ejemplo Adobe Experience Platform, sistema de reservación. |
| **[!UICONTROL Event]** | Lista de todos los eventos (nombre del **evento - etiqueta** de evento) utilizados en viajes, por ejemplo, evento de Geometrixx - salida de Geometrixx. |
| **Grupo de campos** | Lista de los grupos de campo (nombre **del grupo de** campo) utilizados para enriquecer los datos en los viajes, por ejemplo, el grupo de campo de Perfil, el sistema de reserva de Geometrixx. |
| **Recorrido** | Lista de cada viaje (nombre **del** viaje) en modo de prueba y activo, por ejemplo, abandono del carro de compras, notificación de reserva de hoteles. |
| **Versión de viaje** | Lista de cada versión publicada de un viaje (nombre del **viaje + número** de versión), por ejemplo: abandono del carro v1, notificación de reserva del hotel v2. |
| **Orquestación** | Lista de cada actividad de orquestación (**Condición, Fin, Espera**) definida y utilizada en los viajes. |

## Dimensiones de envío {#delivery-dimensions}

La tabla siguiente le proporciona la lista de las dimensiones de envío utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Dimensión | Definición |
|--- |--- |
| **Explorador** | Explorador desde el que se abrió o en el que se hizo clic en el mensaje. |
| **Nombre del envío** | Etiqueta e ID del envío. |
| **Dispositivo** | Dispositivo desde el cual se abrió/visualizó/hizo clic la notificación por correo electrónico/SMS/push. |
| **Tipo de mensaje** | Canal utilizado para el envío, como correo electrónico, SMS, notificación push o In-App. |
| **Nombre de la aplicación móvil** | Nombre de la aplicación móvil |
| **Plataforma** | Plataforma del dispositivo desde el que se abrió/visualizó/hizo clic en el mensaje. |
| **[!UICONTROL Push platform]** | Plataforma del dispositivo desde el que se abrió la notificación push, como iOS o Android. |
| **Dominio de destinatario** | Dominio utilizado para abrir el correo electrónico. |
| **URL de seguimiento** | Dirección URL en la que el usuario hizo clic desde el mensaje. |
| **Categoría de URL de seguimiento** | Categoría asignada a la URL de seguimiento. |
| **Etiqueta de URL de seguimiento** | Etiqueta dada a la dirección URL, como página espejo, contacto con nosotros o abrir. |
| **Variante** | Variante del correo electrónico en caso de prueba A/B. |

## Métricas de viajes {#MBE_p_p22_c4j_w2b}

La tabla siguiente le proporciona la lista de las métricas utilizadas en los informes de viaje, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |---|
| **Completado** | Número total de individuos que finalizaron normalmente el viaje. |
| **Tasa de finalización** | El número total de personas que finalizaron normalmente el viaje, en comparación con el número total de personas que entraron en él. |
| **Actual** | Número total de individuos que se encuentran en el viaje, es decir, cuántas personas entraron menos las que salieron, errores y tiempo de espera agotado. |
| **Tasa actual** | El número total de personas que se encuentran en el viaje en comparación con el número de personas que han entrado en el viaje. |
| **Introducido** | Número total de eventos que se produjeron para el inicio de una entrada individual en el viaje. |
| **Error** | Número total de errores que se produjeron durante un viaje pero que no impidieron que el viaje fuera exitoso. |
| **Error en la acción** | Número total de errores que se produjeron en las acciones. |
| **Error en el Enriquecimiento** | Número total de errores que se produjeron en un enriquecimiento de datos al llamar a un origen o grupo de campos de datos. |
| **Error en el Evento** | Número total de errores que se produjeron en eventos. |
| **Tasa de error** | Número total de errores que se produjeron durante un viaje en comparación con el número total de ocurrencias en el mismo. |
| **Acción ejecutada** | Número total de acciones ejecutadas para un viaje. |
| **Enriquecimiento ejecutado** | Número total de enriquecimientos ejecutados llamando a un origen de datos para obtener grupos de campos específicos. |
| **Evento ejecutado** | Número total de acciones ejecutadas para un viaje. |
| **Orquestación ejecutada** | Número total de objetos de orquestación (fin, espera, condición) ejecutados para un viaje. |
| **Error** | Número total de viajes que no se ejecutaron correctamente. |
| **Tasa de error** | Número total de viajes que no se ejecutaron correctamente en comparación con el número de viajes de ejecución. |

## Métricas de envío {#delivery-metrics}

La tabla siguiente le proporciona la lista de las métricas utilizadas en los informes de periodicidad, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |--- |
| **En lista de bloqueados** | Número de destinatarios que declararon un correo electrónico como correo no deseado o no deseado. |
| **Tasa de lista de bloqueados** | Número total de mensajes en lista de bloqueados en comparación con los mensajes enviados. |
| **Devoluciones + errores** | Total de errores acumulados durante el envío y el procesamiento de devolución automático en relación con el número total de mensajes enviados. |
| **Devoluciones + tasa de error** | Número total de mensajes devueltos en comparación con los mensajes enviados. |
| **Haga clic en** | Número de veces que se hizo clic en un contenido en un envío. |
| **Tasa de pulsaciones** | Número total de clics en un envío en comparación con el número de mensajes enviados. |
| **Entrega** | Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados. |
| **Tasa de entrega** | Número total de mensajes enviados correctamente en comparación con los mensajes enviados. |
| **Error** | Número total de errores que se produjeron durante un viaje pero que no impidieron que el viaje fuera exitoso. |
| **Rebotes duros** | Número total de errores permanentes, como una dirección de correo electrónico incorrecta. |
| **Tasa de salida hacia otro sitio** | Número total de envíos que fallaron debido a errores permanentes en comparación con los mensajes enviados. |
| **Página espejo** | Número de destinatarios que hicieron clic en el vínculo de página espejo. |
| **Tasa de página espejo** | Número total de clics en el vínculo de página espejo en comparación con el total de mensajes enviados. |
| **Apertura** | Número de veces que se abrió un mensaje en un envío. |
| **Tasa de apertura** | Número total de mensajes abiertos en comparación con el número de mensajes entregados. |
| **Cuarentena** | Número de mensajes que se rebotaron y resultaron en la cuarentena de la dirección. |
| **Tasa de cuarentena** | Número total de cuarentenas en comparación con los mensajes enviados. |
| **Rechazado** | Número de mensajes clasificados como correo no deseado por los servidores SMTP. |
| **Tipo rechazado** | Número total de mensajes marcados como rechazados en comparación con los mensajes enviados. |
| **Procesado/enviado** | Número total de envíos para el envío. |
| **Rebote suave** | Número total de errores temporales, como una bandeja de entrada completa. |
| **Tasa de salida hacia otro sitio suave** | Número total de envíos que fallaron por un motivo temporal en comparación con los mensajes enviados. |
| **Clics únicos** | Número de destinatarios que hicieron clic en un contenido de un envío. |
| **Aperturas únicas** | Número de destinatarios que abrieron el envío. |
| **No suscrito** | Número de clics en el vínculo de baja de suscripción. |
| **Tasa de cancelación de suscripción** | Número total de cancelaciones de suscripción por destinatario en comparación con los mensajes enviados. |
