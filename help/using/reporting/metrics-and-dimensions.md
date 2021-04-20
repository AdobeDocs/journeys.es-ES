---
product: adobe campaign
solution: Journey Orchestration
title: Métricas y dimensiones
description: Obtenga información sobre las dimensiones y métricas disponibles para el Journey Orchestration
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 2%

---


# Métricas y dimensiones {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Los datos de envío solo se rellenarán si tiene Adobe Campaign Standard.

Aquí puede encontrar la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.

La tabla siguiente proporciona la lista de dimensiones utilizadas en los informes de recorrido y sus definiciones.

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte [esta página](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensiones de recorrido {#MBE_table_wk4_bnj_w2b}

La tabla siguiente proporciona la lista de dimensiones utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Dimension | Definición |
|--- |--- |
| **Acción** | Lista de todas las acciones (**nombre de acción - etiqueta de acción**) utilizadas en recorridos como, por ejemplo, Push - Check out confirmation, Email - Rewards fidelity. |
| **Fuente de datos** | Lista de fuentes de datos (**nombre de fuente de datos**) utilizadas para enriquecer los datos en un recorrido, por ejemplo, Adobe Experience Platform, sistema de reserva. |
| **[!UICONTROL Event]** | Lista de todos los eventos (**nombre del evento - etiqueta de evento**) utilizados en recorridos como, por ejemplo, evento de Geometrixx - salida de Geometrixx. |
| **Grupo de campos** | Lista de grupos de campos (**nombre del grupo de campos**) utilizados para enriquecer datos en recorridos como, por ejemplo, grupo de campos de perfil o sistema de reserva de Geometrixx. |
| **Recorrido** | Lista de cada recorrido (**nombre de recorrido**) en modo de prueba y activo, por ejemplo, abandono del carro de compras, notificación de reserva del hotel. |
| **Versión de recorrido** | Lista de todas las versiones publicadas de un recorrido (**nombre del recorrido + número de versión**), por ejemplo Abandono del carro de compras v1, Notificación de reserva del hotel v2. |
| **Organización** | Lista de todas las actividades de orquestación (**Condition, End, Wait**) definidas y utilizadas en recorridos. |

## Dimensiones de envío {#delivery-dimensions}

La tabla siguiente proporciona la lista de dimensiones de envío utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Dimensión | Definición |
|--- |--- |
| **Navegador** | Explorador desde el que se abrió o se hizo clic en el mensaje. |
| **Nombre de la entrega** | Etiqueta e ID de la entrega. |
| **Dispositivo** | Dispositivo desde el que se abrió, visualizó o hizo clic en la notificación de correo electrónico/SMS/push. |
| **Tipo de mensaje** | Canal utilizado para el envío, como correo electrónico, SMS, notificaciones push o en la aplicación. |
| **Nombre de la aplicación móvil** | Nombre de la aplicación móvil |
| **Plataforma** | Plataforma del dispositivo desde el que se abrió, visualizó o hizo clic en el mensaje. |
| **[!UICONTROL Push platform]** | Plataforma del dispositivo desde el que se abrió la notificación push, como iOS o Android. |
| **Dominio de destinatario** | Dominio utilizado para abrir el correo electrónico. |
| **URL de seguimiento** | Dirección URL en la que el usuario hizo clic desde el mensaje. |
| **Categoría de URL de seguimiento** | Categoría asignada a la dirección URL de seguimiento. |
| **Etiqueta de URL de seguimiento** | Etiqueta dada a la dirección URL, como página espejo, póngase en contacto con nosotros o abra. |
| **Variant** | Variant del correo electrónico en caso de prueba A/B. |

## Métricas de recorrido {#MBE_p_p22_c4j_w2b}

La tabla siguiente proporciona la lista de métricas utilizadas en los informes de recorrido, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |---|
| **Completado** | Número total de individuos que finalizaron normalmente el recorrido. |
| **Tasa de finalización** | Número total de personas que terminaron normalmente con el recorrido en comparación con el número total de personas que entraron en el recorrido. |
| **Actual** | Número total de personas que actualmente están en el recorrido, es decir, cuántas personas entraron menos las que salieron, los errores y el tiempo de espera agotado. |
| **Tasa actual** | Número total de personas actualmente en el recorrido en comparación con el número de personas que ingresaron al recorrido. |
| **Introducido** | Número total de eventos que se produjeron para iniciar una entrada individual en el recorrido. |
| **Error** | Número total de errores que se produjeron durante un recorrido pero que no impidieron que el recorrido se realizara correctamente. |
| **Error en acción** | Número total de errores que se produjeron en las acciones. |
| **Error en el enriquecimiento** | Número total de errores que se produjeron para un enriquecimiento de datos al llamar a una fuente de datos o a un grupo de campos. |
| **Error en el evento** | Número total de errores que se produjeron en los eventos. |
| **Tasa de error** | Número total de errores que se produjeron durante un recorrido en comparación con el número total de ocurrencias en el recorrido. |
| **Acción ejecutada** | Número total de acciones ejecutadas para un recorrido. |
| **Enriquecimiento ejecutado** | Número total de enriquecimientos ejecutados llamando a una fuente de datos para obtener grupos de campos específicos. |
| **Evento ejecutado** | Número total de acciones ejecutadas para un recorrido. |
| **Organización ejecutada** | Número total de objetos de organización (fin, espera, condición) ejecutados para un recorrido. |
| **Error** | Número total de recorridos que no se ejecutaron correctamente. |
| **Tasa de error** | Número total de recorridos que no se ejecutaron correctamente comparados con el número de recorridos en ejecución. |

## Métricas de envío {#delivery-metrics}

La tabla siguiente le proporciona la lista de métricas utilizadas en los recorridos
informes, sus definiciones y fórmulas.

| Métrica | Definición |
|--- |--- |
| **En lista de bloqueados** | Número de destinatarios que han declarado un correo electrónico como correo no deseado o no deseado. |
| **tasa de lista de bloqueados** | Número total de mensajes en lista de bloqueados en comparación con los mensajes enviados. |
| **Devoluciones + errores** | Total de errores acumulados durante la entrega y el procesamiento automático de devoluciones en relación con la cantidad total de mensajes enviados. |
| **Devoluciones + tasa de error** | Número total de mensajes devueltos en comparación con los mensajes enviados. |
| **Haga clic en** | Número de veces que se hizo clic en un contenido en una entrega. |
| **Tasa de pulsaciones** | Número total de clics en una entrega en comparación con el número de mensajes enviados. |
| **Entrega** | Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados. |
| **Tasa de entrega** | Número total de mensajes enviados correctamente comparados con los mensajes enviados. |
| **Error** | Número total de errores que se produjeron durante un recorrido pero que no impidieron que el recorrido se realizara correctamente. |
| **Rechazo grave** | Número total de errores permanentes, como una dirección de correo electrónico incorrecta. |
| **Tasa de salida hacia otro sitio** | Número total de envíos que fallaron debido a errores permanentes en comparación con los mensajes enviados. |
| **Página espejo** | Número de destinatarios que hicieron clic en el vínculo de la página espejo. |
| **Tasa de página espejo** | Número total de clics en el vínculo de la página espejo en comparación con el total de mensajes enviados. |
| **Apertura** | Número de veces que se abrió un mensaje en una entrega. |
| **Tasa de apertura** | Número total de mensajes abiertos comparados con el número de mensajes enviados. |
| **Cuarentena** | Número de mensajes que se rebotaron y que dieron como resultado la cuarentena de la dirección. |
| **Tasa de cuarentena** | Número total de cuarentenas en comparación con los mensajes enviados. |
| **Rechazado** | Número de mensajes clasificados como correo no deseado por los servidores SMTP. |
| **Tasa rechazada** | Número total de mensajes marcados como rechazados en comparación con los mensajes enviados. |
| **Procesado/enviado** | Número total de envíos para la entrega. |
| **Rechazo suave** | Número total de errores temporales, como una bandeja de entrada completa. |
| **Tasa de devoluciones suave** | Número total de envíos que fallaron por un motivo temporal en comparación con los mensajes enviados. |
| **Clics únicos** | Número de destinatarios que hicieron clic en un contenido de una entrega. |
| **Aperturas únicas** | Número de destinatarios que abrieron la entrega. |
| **Cancelación de suscripción** | Número de clics en el vínculo de baja de suscripción. |
| **Tasa de cancelación de suscripción** | Número total de bajas de suscripción por destinatario en comparación con los mensajes enviados. |
