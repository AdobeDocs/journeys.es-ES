---
title: Actualizaciones de documentación
description: Más información sobre las actualizaciones de documentación
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
source-git-commit: 5d92b9d70a70700026a4715c6cb6a6c4ba565ba5
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 60%

---


# Actualizaciones de documentación

Esta página lista todas las actualizaciones de documentación de [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## Julio de 2020 {#july-2020}

* Se Añadió una nueva sección sobre las características Alpha que se prueban entre un conjunto limitado de clientes. [Más información](../alpha/alpha-overview.md)
* Añadió una nueva sección sobre la integración con Servicios inteligentes. [Más información](../ai-services/ai-services-overview.md)
* Se Añadió una nueva sección sobre la creación del perfil de prueba. [Más información](../building-journeys/testing-the-journey.md#create-test-profile).
* Información Añadida sobre cómo utilizar el nodo **SegmentQualification** en una condición de viaje o acción. [Más información](../building-journeys/event-activities.md#segment-qualification).
* Se ha añadido una nota al mensaje transaccional de Campaña y a la publicación de eventos. Consulte [](../action/working-with-adobe-campaign.md) y [](../building-journeys/using-adobe-campaign-actions.md).
* Se ha añadido información sobre las comprobaciones que se realizan al probar la URL de la instancia de Campaign Standard. [Más información](../action/working-with-adobe-campaign.md)
* Se ha añadido información sobre la compatibilidad de eventos de reacción con instancias de Campaign Standard alojadas en servidores AWS o Azure. [Más información](../building-journeys/event-activities.md#section_dhx_gss_dgb)
* Se ha agregado una nota sobre la necesidad de configurar una regla de límite al trabajar con mensajes transaccionales de Campaign Standard. [Más información](../action/working-with-adobe-campaign.md)
* Se ha añadido una nota a la generación de eventos reales al activar eventos mediante el modo de prueba. [Más información](../building-journeys/testing-the-journey.md#firing_events)

## Junio de 2020 {#june-2020}

* Información Añadida sobre cómo cambiar la duración de la caché del token para un origen de datos de autenticación personalizada. [Más información](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Capturas de pantalla y texto actualizados para reflejar el cambio de nombre del estado del viaje **finalizado** , que se ha cambiado a **Cerrado (sin entrada)**.
* Información Añadida sobre cómo se define el idioma para la interfaz. [Más información](../about/user-interface.md)
* La lista de los estados del viaje de un individuo se ha trasladado a la sección de registros [del modo de](../building-journeys/testing-the-journey.md#viewing_logs) prueba.

## de abril de 2020 {#april-2020}

* Se ha Añadido una nueva sección sobre la definición de esquema de evento de experiencias para ayudar a los usuarios a configurar su primer evento. [Más información](../event/experience-event-schema.md)
* La página de inicio de [!DNL Journey Orchestration] documentación se ha actualizado con vínculos útiles adicionales. [Más información](../../journey-orchestration-home.md)

## Marzo de 2020 {#march-2020}

* Descripciones de parámetros añadidos en _actionExecutionErrors_ y _fetchErrors_ en la sección de registros de pruebas. [Más información](../building-journeys/testing-the-journey.md#viewing_logs)
* Se han actualizado las limitaciones de las acciones personalizadas utilizadas en un recorrido. También puede modificar el campo **URL** y los parámetros **Autenticación** . [Más información](../action/about-custom-action-configuration.md)
* Se han agregado nuevas entradas de ayuda contextual. El panel de carga útil de autenticación personalizada (en acciones y fuentes de datos) ahora incluye un icono de ayuda que se vincula a esta [sección](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Ahora se pueden detener los viajes cerrados. [Más información](../building-journeys/using-the-journey-designer.md)
* Se ha reorganizado la sección de descripción de la interfaz. [Más información](../about/user-interface.md)
* Se ha añadido la activación de varios eventos a la sección Modo de prueba [Más información](../building-journeys/testing-the-journey.md#firing_events)
* La sección Modo de prueba se ha actualizado con respecto al nuevo parámetro **Tiempo de espera en prueba** . [Más información](../building-journeys/testing-the-journey.md)
* La sección Registro de pruebas se ha actualizado con códigos de error de llamada externa y respuestas. [Más información](../building-journeys/testing-the-journey.md#viewing_logs)
* La administración de zonas horarias ahora está centralizada en el panel de propiedades del recorrido. Lea más [aquí](../building-journeys/changing-properties.md#timezone) y [aquí](../building-journeys/timezone-management.md)
* La sección Diseñador de recorridos se ha actualizado para reflejar las mejoras recientes. [Más información](../building-journeys/using-the-journey-designer.md)
* La descripción de la interfaz se ha actualizado con información sobre la ayuda contextual. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)
* Al examinar los **campos XDM**, ahora se muestra el nombre descriptivo. Se han actualizado las secciones relacionadas. [Más información](../about/user-interface.md#friendly-names-display)

## Febrero de 2020 {#february-2020}

* Se ha actualizado la sección de accesos directos. El método abreviado de teclado **C** le permite crear un nuevo elemento en todas las pantallas de lista. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)
* Se han mejorado las páginas de información general de fuentes [de](../datasource/about-data-sources.md) datos y [acciones](../action/action.md) .

## Enero de 2020 {#january-2020}

* Se han agregado limitaciones de captura para [eventos de experiencias](../datasource/adobe-experience-platform-data-source.md) y [segmentos](../functions/functioninsegment.md).
* La documentación de [getBestSendTime](../functions/functiongetbestsendtime.md) se ha actualizado.

## Diciembre de 2019 {#december-2019}

* Todas las capturas de pantalla se han actualizado para reflejar los cambios en la interfaz.
* Se ha actualizado la sección del modo de prueba. [Más información](../building-journeys/testing-the-journey.md)
* Se ha añadido una advertencia en las secciones de [optimización del tiempo de envío de correo electrónico](../building-journeys/wait-activity.md) y [puntuaciones de fatiga predictiva](../ai-services/leveraging-fatigue-scores.md). Estas funciones solo están disponibles para los clientes que utilizan la función de servicio de datos de Adobe Campaign Standard.
* Ahora se pueden eliminar los recorridos interrumpidos. Se han actualizado las páginas de documentación relacionadas.
* Ahora se muestran dos colores cuando se detectan problemas en un recorrido. Rojo para errores y naranja para advertencias. [Más información](../about/troubleshooting.md)
* Se ha actualizado la sección del editor de expresiones avanzado. [Más información](../expression/expressionadvanced.md).
* Se han movido y actualizado las secciones [Instrucción condicional](../expression/conditional-instruction.md) y [administración de colecciones](../expression/collection-management-functions.md).
* La sección de [funciones](../expression/functions.md) se ha actualizado con nuevos ejemplos.
* La documentación de la [función toDateTime](../functions/functiontodatetime.md) se ha actualizado para reflejar los cambios de sintaxis de zona horaria.
