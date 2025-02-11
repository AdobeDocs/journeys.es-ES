---
product: adobe campaign
title: Actualizaciones de documentación
description: Más información sobre las actualizaciones de documentación
feature: Journeys
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: af224593ca69f79c3e4458f26f77b92197ad73a2
workflow-type: ht
source-wordcount: '1010'
ht-degree: 100%

---

# Actualizaciones de documentación

Esta página enumera todas las actualizaciones de documentación de [!DNL Journey Orchestration].
También puede consultar las [!DNL Journey Orchestration] [Notas de la versión](../release-notes/release-notes.md).

## Julio de 2022 {#july-2022}

* En las propiedades del recorrido, la opción **Zona horaria del perfil** ahora está desactivada de forma predeterminada. [Más información](../building-journeys/timezone-management.md#timezone-from-profiles)
* En la actividad **Espera**, la opción **Fecha fija** ya no está disponible. [Más información](../building-journeys/wait-activity.md)

## Junio de 2022 {#june-2022}

* Se han añadido nuevos ejemplos de consultas a esta [página](../building-journeys/query-examples.md)

## Marzo de 2022 {#march-2022}

* Se ha añadido un ejemplo sobre cómo agregar una expresión como valor predeterminado en el editor de expresiones. [Más información](../expression/field-references.md#default-value)

## Febrero de 2022 {#feb-2022}

* Las páginas de documentación de la función [replace](../functions/functionreplace.md#example_2) y [replaceAll](../functions/functionreplaceall.md#example) se han actualizado con información y ejemplos adicionales relacionados con el parámetro del público destinatario.
* Se han añadido las prácticas recomendadas a la página de [Operadores](../expression/operators.md#important-notes).

## Septiembre de 2021

* Se han actualizado las siguientes páginas de funciones: [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* Se han añadido las siguientes funciones: [filter](../functions/functionfilter.md), [intersect](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* El tipo de fecha dateOnly se ha añadido a la documentación del editor de expresiones. [Más información](../expression/data-types.md)

* Se han añadido detalles sobre la duración de la caché de acciones personalizada. [Más información](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Se ha añadido información sobre los puertos predeterminados de acciones personalizadas. [Más información](../action/url-configuration.md)

* Se han añadido ejemplos de uso común para consultar eventos de pasos de recorrido en un lago de datos. [Más información](../building-journeys/query-examples.md)

## Agosto de 2021

* Se ha actualizado el procedimiento de configuración para acciones personalizadas con rutas URL dinámicas y encabezados dinámicos. [Más información](../action/url-configuration.md)
* Se ha añadido una sección acerca de las funciones de accesibilidad. [Más información](../about/user-interface.md#accessibility)
* Se ha añadido una sección acerca de métodos de evaluación de segmentos. [Más información](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## Marzo de 2021 {#march-2021}

* Hemos detallado el procedimiento completo para crear perfiles de prueba en Adobe Experience Platform. [Más información](../building-journeys/creating-test-profiles.md).

## Enero de 2021 {#january-2021}

* Se han añadido prácticas recomendadas al activar un recorrido al mismo tiempo que la creación de un perfil. [Más información](../about/limitations.md#journeys-limitation-profile-creation).

## Octubre de 2020 {#october-2020}

* Se ha añadido información sobre cómo configurar un tiempo de espera para un evento. [Más información](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## Septiembre de 2020 {#september-2020}

* La sección de descripción de la interfaz se ha actualizado para reflejar el nuevo menú **All selector**. [Más información](../about/user-interface.md)
* Se ha añadido una nota sobre las nuevas versiones de los recorridos basados en segmentos que no son recurrentes.

## Agosto de 2020 {#august-2020}

* Información añadida sobre cómo ordenar y elegir las columnas que se mostrarán en la lista de segmentos. [Más información](../building-journeys/segment-qualification-events.md)
* Se añadió información sobre cómo copiar el nombre y la ID de un segmento después de seleccionarlo. [Más información](../building-journeys/segment-qualification-events.md)
* Las ocurrencias de Experience Platform se han unificado en las diferentes páginas.

## Julio de 2020 {#july-2020}

* Se ha añadido un vínculo a un nuevo vídeo de tutorial sobre el sistema de informes de eventos del paso a Adobe Experience Platform. [Más información](../building-journeys/sharing-overview.md)
* La sección actividades de eventos se ha reorganizado en subsecciones específicas para cada tipo de evento. [Más información](../building-journeys/event-activities.md)
* Prácticas recomendadas añadidas para evitar sobrecargas con la calificación de segmentos. [Más información](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Añadió una nota para explicar cómo continuar un recorrido después de un error en una acción o condición. [Más información](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Se ha añadido una nueva sección sobre las funciones alfa que se prueban entre un conjunto limitado de clientes.
* Se añadió una nueva sección sobre la integración con servicios inteligentes. [Más información](../ai-services/ai-services-overview.md)
* Se añadió una nueva sección sobre la creación del perfil de prueba. [Más información](../building-journeys/testing-the-journey.md)
* Se añadió información sobre cómo utilizar el nodo **[!UICONTROL SegmentQualification]** en una condición de recorrido o acción. [Más información](../building-journeys/segment-qualification-events.md)
* Se añadió una nota al mensaje transaccional de Campaign y a la publicación de eventos. Consulte [Uso de Adobe Campaign](../action/working-with-adobe-campaign.md) y [Uso de acciones](../building-journeys/using-adobe-campaign-actions.md) de Adobe Campaign.
* Se añadió información sobre las comprobaciones que se realizan al probar la URL de la instancia de Campaign Standard. [Más información](../action/working-with-adobe-campaign.md)
* Se añadió información sobre la compatibilidad de eventos de reacción con instancias de Campaign Standard alojadas en servidores AWS o Azure. [Más información](../building-journeys/reaction-events.md)
* Se añadió una nota sobre la necesidad de configurar una regla de límite al trabajar con mensajes transaccionales de Campaign Standard. [Más información](../action/working-with-adobe-campaign.md)
* Se añadió una nota a la generación de eventos reales al activar eventos mediante el modo de prueba. [Más información](../building-journeys/testing-the-journey.md#firing_events)

## Junio de 2020 {#june-2020}

* Se añadió información sobre cómo cambiar la duración de caché del token para una fuente de datos de autenticación personalizada. [Más información](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Capturas de pantalla y texto actualizados para reflejar el cambio de nombre del estado del recorrido **[!UICONTROL Finished]** , que se ha cambiado a **[!UICONTROL Closed (no entrance)]**.
* Se añadió información sobre cómo se define el idioma para la interfaz. [Más información](../about/user-interface.md)
* La lista de los estados del recorrido de un individuo se ha trasladado a la sección de [registros del modo de prueba ](../building-journeys/testing-the-journey.md#viewing_logs).

## Abril de 2020 {#april-2020}

* Se añadió una nueva sección sobre la definición de esquema de evento de experiencias para ayudar a los usuarios a configurar su primer evento. [Más información](../event/experience-event-schema.md)
* La página de inicio de la documentación de [!DNL Journey Orchestration] se ha actualizado con vínculos útiles adicionales. [Más información](../../journey-orchestration-home.md)

## Marzo de 2020 {#march-2020}

* Descripciones de parámetros añadidos en _actionExecutionErrors_ y _fetchErrors_ en la sección de registros de pruebas. [Más información](../building-journeys/testing-the-journey.md#viewing_logs)
* Se han actualizado las limitaciones de las acciones personalizadas utilizadas en un recorrido. También puede modificar el campo **[!UICONTROL URL]** y los parámetros **[!UICONTROL Authentication]** . [Más información](../action/about-custom-action-configuration.md)
* Se han agregado nuevas entradas de ayuda contextual. El panel de carga útil de autenticación personalizada (en acciones y fuentes de datos) ahora incluye un icono de ayuda que se vincula a esta [sección](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Ahora se pueden cerrar los recorridos finalizados. [Más información](../building-journeys/using-the-journey-designer.md)
* Se ha reorganizado la sección de descripción de la interfaz. [Más información](../about/user-interface.md)
* Se ha añadido la activación de varios eventos a la sección Modo de prueba [Más información](../building-journeys/testing-the-journey.md#firing_events)
* Se ha actualizado la sección del modo de prueba con respecto al nuevo parámetro **[!UICONTROL Wait time in test]** . [Más información](../building-journeys/testing-the-journey.md)
* La sección Registro de pruebas se ha actualizado con códigos de error de llamada externa y respuestas. [Más información](../building-journeys/testing-the-journey.md#viewing_logs)
* La administración de zonas horarias ahora está centralizada en el panel de propiedades del recorrido. Lea más [aquí](../building-journeys/changing-properties.md#timezone) y [aquí](../building-journeys/timezone-management.md)
* La sección Diseñador de recorridos se ha actualizado para reflejar las mejoras recientes. [Más información](../building-journeys/using-the-journey-designer.md)
* La descripción de la interfaz se ha actualizado con información sobre la ayuda contextual. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)
* Al examinar los **campos XDM**, ahora se muestra el nombre descriptivo. Se han actualizado las secciones relacionadas. [Más información](../about/user-interface.md#friendly-names-display)

## Febrero de 2020 {#february-2020}

* Se ha actualizado la sección de accesos directos. El método abreviado de teclado **C** le permite crear un nuevo elemento en todas las pantallas de lista. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)
* Se mejoraron las páginas de información general de [fuentes de datos](../datasource/about-data-sources.md) y [acciones](../action/action.md) .

## Enero de 2020 {#january-2020}

* Se han agregado limitaciones de captura para [eventos de experiencias](../datasource/adobe-experience-platform-data-source.md) y [segmentos](../functions/functioninsegment.md).
  <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## Diciembre de 2019 {#december-2019}

* Todas las capturas de pantalla se han actualizado para reflejar los cambios en la interfaz.
* Se ha actualizado la sección del modo de prueba. [Más información](../building-journeys/testing-the-journey.md)
  <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* Ahora se pueden eliminar los recorridos interrumpidos. Se han actualizado las páginas de documentación relacionadas.
* Ahora se muestran dos colores cuando se detectan problemas en un recorrido. Rojo para errores y naranja para advertencias. [Más información](../about/troubleshooting.md)
* Se ha actualizado la sección del editor de expresiones avanzado. [Más información](../expression/expressionadvanced.md).
* Se han movido y actualizado las secciones [Instrucción condicional](../expression/conditional-instruction.md) y [administración de colecciones](../expression/collection-management-functions.md).
* La sección de [funciones](../expression/functions.md) se ha actualizado con nuevos ejemplos.
* La documentación de la [función toDateTime](../functions/functiontodatetime.md) se ha actualizado para reflejar los cambios de sintaxis de zona horaria.
