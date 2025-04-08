---
product: adobe campaign
title: Métricas y dimensiones
description: Obtenga información sobre las dimensiones y métricas disponibles para Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 3%

---

# Métricas y dimensiones {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


>[!NOTE]
>
>Los datos de la entrega solo se rellenarán si tiene Adobe Campaign Standard.

Aquí puede encontrar la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.

La siguiente tabla le proporciona la lista de dimensiones utilizadas en los informes de recorrido y sus definiciones.

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## dimensiones de recorrido {#MBE_table_wk4_bnj_w2b}

La siguiente tabla le proporciona la lista de dimensiones utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Dimensiones | Definición |
|--- |--- |
| **Acción** | Lista de todas las acciones (**action name - action label**) utilizadas en los recorridos; por ejemplo, Push - Check out confirmation, Correo electrónico - Rewards fidelity. |
| **Origen de datos** | Lista de orígenes de datos (**nombre de origen de datos**) que se usan para enriquecer datos en un recorrido, por ejemplo, Adobe Experience Platform, Sistema de reservas. |
| **[!UICONTROL Event]** | Lista de todos los eventos (**nombre del evento - etiqueta de evento**) utilizados en recorridos, por ejemplo: evento de Geometrixx - Desprotección de Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (**nombre de grupo de campos**) utilizados para enriquecer datos en recorridos como, por ejemplo, grupo de campos de perfil, sistema de reserva de Geometrixx. |
| **Recorrido** | Lista de todos los recorridos (**nombre del recorrido**) en el modo de prueba y activos, por ejemplo: abandono del carro de compras, notificación de reservación de hotel. |
| **Versión de Recorrido** | Lista de todas las versiones publicadas de un recorrido (**nombre del recorrido + número de versión**), por ejemplo: abandono del carro de compras v1, notificación de reservaciones de hoteles v2. |
| **Orquestación** | Lista de todas las actividades de orquestación (**Condición, Fin, Espera**) definidas y utilizadas en los recorridos. |

## Dimensiones de envío {#delivery-dimensions}

La siguiente tabla le proporciona la lista de dimensiones de envío utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Dimensión | Definición |
|--- |--- |
| **Explorador** | Explorador desde el que se abrió o se hizo clic en el mensaje. |
| **Nombre de entrega** | Etiqueta e ID de envío. |
| **Dispositivo** | Dispositivo desde el que se abrió, vio o hizo clic la notificación push/SMS/de correo electrónico. |
| **Tipo de mensaje** | Canal utilizado para el envío, como correo electrónico, SMS, notificación push o en la aplicación. |
| **Nombre de aplicación móvil** | Nombre de la aplicación móvil |
| **Plataforma** | Plataforma del dispositivo desde el que se abrió, visualizó o hizo clic en el mensaje. |
| **[!UICONTROL Push platform]** | Plataforma del dispositivo desde el que se abrió la notificación push como, por ejemplo, iOS o Android. |
| **Dominio del destinatario** | Dominio utilizado para abrir el correo electrónico. |
| **URL de seguimiento** | URL en la que el usuario hizo clic desde el mensaje. |
| **Categoría de URL de seguimiento** | Categoría asignada a la URL de seguimiento. |
| **Etiqueta de URL de seguimiento** | Etiqueta proporcionada a la dirección URL, como una página espejo, póngase en contacto con nosotros o abra. |
| **Variante** | Variante del correo electrónico en el caso de las pruebas A/B. |

## Métricas de recorrido {#MBE_p_p22_c4j_w2b}

La siguiente tabla le proporciona la lista de métricas utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |---|
| **Completado** | Número total de individuos que finalizaron normalmente el recorrido. |
| **Tasa de finalización** | Número total de individuos que finalizaron normalmente el recorrido comparado con el número total de individuos que entraron en el recorrido. |
| **Actual** | Número total de personas que están actualmente en el recorrido, es decir, cuántas personas ingresaron menos personas que salieron, errores y tiempo de espera agotado. |
| **Tasa actual** | Número total de personas que están actualmente en el recorrido comparadas con el número de personas que entraron en el recorrido. |
| **Ingresó** | Número total de eventos que se produjeron para iniciar una entrada individual en el recorrido. |
| **Error** | Número total de errores que se produjeron durante un recorrido pero que no impidieron que el recorrido se realizara correctamente. |
| **Error en acción** | Número total de errores que se produjeron para las acciones. |
| **Error en enriquecimiento** | Número total de errores que se produjeron para un enriquecimiento de datos al llamar a una fuente de datos o grupo de campos. |
| **Error en evento** | Número total de errores que se produjeron en los eventos. |
| **Tasa de error** | Número total de errores que se produjeron durante un recorrido comparado con el número total de incidencias en el recorrido. |
| **Acción ejecutada** | Número total de acciones ejecutadas para un recorrido. |
| **Enriquecimiento ejecutado** | Número total de enriquecimientos ejecutados al llamar a una fuente de datos para obtener grupos de campos específicos. |
| **Evento ejecutado** | Número total de acciones ejecutadas para un recorrido. |
| **Orquestación ejecutada** | Número total de objetos de orquestación (fin, espera, condición) ejecutados para un recorrido. |
| **Fallido** | Número total de recorridos que no se ejecutaron correctamente. |
| **Tasa de errores** | Número total de recorridos que no se ejecutaron correctamente en comparación con el número de recorridos de ejecución. |

## Métricas de envío {#delivery-metrics}

La siguiente tabla le proporciona la lista de métricas utilizadas en el recorrido
informes, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |--- |
| **En lista de bloqueados** | Número de destinatarios que han declarado un correo electrónico como no deseado o no deseado. |
| **tasa de Lista de bloqueados** | Número total de mensajes en la lista de bloqueados comparados con los mensajes enviados. |
| **Devoluciones + errores** | Total de errores acumulados durante el envío y el procesamiento automático de devoluciones en relación con el número total de mensajes enviados. |
| **Rebote + tasa de error** | Número total de mensajes devueltos en comparación con los mensajes enviados. |
| **Hacer clic** | Número de veces que se hizo clic en un contenido en una entrega. |
| **Tasa de pulsaciones** | Número total de clics en una entrega comparado con el número de mensajes enviados. |
| **Entregado** | Número de mensajes enviados correctamente en relación con el número total de mensajes enviados. |
| **Tasa de entrega** | Número total de mensajes enviados correctamente en comparación con los mensajes enviados. |
| **Error** | Número total de errores que se produjeron durante un recorrido pero que no impidieron que el recorrido se realizara correctamente. |
| **Rechazo fuerte** | Número total de errores permanentes, como una dirección de correo electrónico incorrecta. |
| **Tasa de salida hacia otro sitio difícil** | Número total de envíos que fallaron debido a errores permanentes en comparación con los mensajes enviados. |
| **Página espejo** | Número de destinatarios que hicieron clic en el vínculo de la página espejo. |
| **Tasa de páginas espejo** | Número total de clics en el vínculo de la página espejo comparados con el total de mensajes enviados. |
| **Abri** | Número de veces que se ha abierto un mensaje en una entrega. |
| **Tasa de apertura** | Número total de mensajes abiertos en comparación con el número de mensajes enviados. |
| **Cuarentena** | Número de mensajes que rebotaron y que dieron lugar a la cuarentena de la dirección. |
| **Tasa de cuarentena** | Número total de cuarentenas comparadas con los mensajes enviados. |
| **Rechazado** | Número de mensajes clasificados como correo no deseado por los servidores SMTP. |
| **Tasa de rechazados** | Número total de mensajes marcados como rechazados en comparación con los mensajes enviados. |
| **Procesado/enviado** | Número total de envíos para el envío. |
| **Rebote suave** | Número total de errores temporales, como una bandeja de entrada llena. |
| **Tasa de salida hacia otro sitio** | Número total de envíos que fallaron debido a un motivo temporal en comparación con los mensajes enviados. |
| **Clics únicos** | Número de destinatarios que hicieron clic en un contenido de una entrega. |
| **Aperturas únicas** | Número de destinatarios que abrieron la entrega. |
| **Canceló la suscripción** | Número de clics en el vínculo de baja de suscripción. |
| **Tasa de cancelación de suscripción** | Número total de bajas de suscripción por destinatario comparado con los mensajes enviados. |
