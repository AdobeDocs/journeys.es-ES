---
product: adobe campaign
title: Métricas y dimensiones
description: Obtenga información acerca de las dimensiones y métricas disponibles para el Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 4%

---

# Métricas y dimensiones {#concept_rfj_wpt_52b}

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
| **Acción** | Lista de cada acción (**nombre de acción - etiqueta de acción**) se utiliza en recorridos, por ejemplo, Push: confirmación de salida, Correo electrónico: fidelidad de recompensas. |
| **Fuente de datos** | Lista de fuentes de datos (**nombre de fuente de datos**) se utiliza para enriquecer datos en un recorrido, por ejemplo, Adobe Experience Platform, Sistema de reservas. |
| **[!UICONTROL Event]** | Lista de cada evento (**nombre del evento: etiqueta de evento**) se utiliza en recorridos, por ejemplo, evento de Geometrixx: salida de Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (**nombre del grupo de campos**) se utiliza para enriquecer datos en recorridos como grupo de campos de perfil o sistema de reserva de Geometrixx. |
| **Recorrido** | Lista de cada recorrido (**nombre del recorrido**) en modo de prueba y activo, por ejemplo, abandono del carro de compras, notificación de reserva de hotel. |
| **versión de recorrido** | Lista de todas las versiones publicadas de un recorrido (**nombre del recorrido + número de versión**), por ejemplo, Abandono del carro de compras v1, Notificación de reserva de hotel v2. |
| **Orquestación** | Lista de todas las actividades de orquestación (**Condición, Fin, Espera**) definida y utilizada en recorridos. |

## Dimensiones de envío {#delivery-dimensions}

La siguiente tabla le proporciona la lista de dimensiones de envío utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Dimensión | Definición |
|--- |--- |
| **Explorador** | Explorador desde el que se abrió o se hizo clic en el mensaje. |
| **Nombre de entrega** | Etiqueta e ID de envío. |
| **Device** | Dispositivo desde el que se abrió, vio o hizo clic la notificación push/SMS/de correo electrónico. |
| **Tipo de mensaje** | Canal utilizado para el envío, como correo electrónico, SMS, notificación push o en la aplicación. |
| **Nombre de aplicación móvil** | Nombre de la aplicación móvil |
| **Plataforma** | Plataforma del dispositivo desde el que se abrió, visualizó o hizo clic en el mensaje. |
| **[!UICONTROL Push platform]** | Plataforma del dispositivo desde el que se abrió la notificación push como, por ejemplo, iOS o Android. |
| **Dominio del destinatario** | Dominio utilizado para abrir el correo electrónico. |
| **URL de seguimiento** | URL en la que el usuario hizo clic desde el mensaje. |
| **Categoría de URL de seguimiento** | Categoría asignada a la URL de seguimiento. |
| **Etiqueta de URL de seguimiento** | Etiqueta proporcionada a la dirección URL, como una página espejo, póngase en contacto con nosotros o abra. |
| **Variante** | Variante del correo electrónico en el caso de las pruebas A/B. |

## métricas de recorrido {#MBE_p_p22_c4j_w2b}

La siguiente tabla le proporciona la lista de métricas utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |---|
| **Completado** | Número total de individuos que finalizaron normalmente el recorrido. |
| **Tasa de finalización** | Número total de individuos que finalizaron normalmente el recorrido comparado con el número total de individuos que entraron en el recorrido. |
| **Actual** | Número total de personas que están actualmente en el recorrido, es decir, cuántas personas ingresaron menos personas que salieron, errores y tiempo de espera agotado. |
| **Tasa actual** | Número total de personas que están actualmente en el recorrido comparadas con el número de personas que entraron en el recorrido. |
| **Ingresado** | Número total de eventos que se produjeron para iniciar una entrada individual en el recorrido. |
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

La siguiente tabla le proporciona la lista de métricas utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |--- |
| **En la lista de bloqueados** | Número de destinatarios que han declarado un correo electrónico como no deseado o no deseado. |
| **tasa de lista de bloqueados** | Número total de mensajes en la lista de bloqueados comparados con los mensajes enviados. |
| **Devoluciones + errores** | Total de errores acumulados durante el envío y el procesamiento automático de devoluciones en relación con el número total de mensajes enviados. |
| **Devolución + tasa de error** | Número total de mensajes devueltos en comparación con los mensajes enviados. |
| **Haga clic en** | Número de veces que se hizo clic en un contenido en una entrega. |
| **Tasa de pulsaciones** | Número total de clics en una entrega comparado con el número de mensajes enviados. |
| **Entregados** | Número de mensajes enviados correctamente en relación con el número total de mensajes enviados. |
| **Tasa de entrega** | Número total de mensajes enviados correctamente en comparación con los mensajes enviados. |
| **Error** | Número total de errores que se produjeron durante un recorrido pero que no impidieron que el recorrido se realizara correctamente. |
| **Rechazo duro** | Número total de errores permanentes, como una dirección de correo electrónico incorrecta. |
| **Tasa de salida hacia otro sitio dura** | Número total de envíos que fallaron debido a errores permanentes en comparación con los mensajes enviados. |
| **Página espejo** | Número de destinatarios que hicieron clic en el vínculo de la página espejo. |
| **Velocidad de página espejo** | Número total de clics en el vínculo de la página espejo comparados con el total de mensajes enviados. |
| **Abri** | Número de veces que se ha abierto un mensaje en una entrega. |
| **Tasa de apertura** | Número total de mensajes abiertos en comparación con el número de mensajes enviados. |
| **Cuarentena** | Número de mensajes que rebotaron y que dieron lugar a la cuarentena de la dirección. |
| **Tasa de cuarentena** | Número total de cuarentenas comparadas con los mensajes enviados. |
| **Rechazado** | Número de mensajes clasificados como correo no deseado por los servidores SMTP. |
| **Tasa de rechazados** | Número total de mensajes marcados como rechazados en comparación con los mensajes enviados. |
| **Procesado/enviado** | Número total de envíos para el envío. |
| **Rechazo suave** | Número total de errores temporales, como una bandeja de entrada llena. |
| **Tasa de devoluciones suaves** | Número total de envíos que fallaron debido a un motivo temporal en comparación con los mensajes enviados. |
| **Clics únicos** | Número de destinatarios que hicieron clic en un contenido de una entrega. |
| **Aperturas únicas** | Número de destinatarios que abrieron la entrega. |
| **Cancelación de suscripción** | Número de clics en el vínculo de baja de suscripción. |
| **Tasa de cancelación de suscripción** | Número total de bajas de suscripción por destinatario comparado con los mensajes enviados. |
