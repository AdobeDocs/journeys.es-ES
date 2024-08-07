---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Guía de Journey Orchestration
user-guide-description: Proporciona instrucciones prácticas para implementar y construir recorridos.
index: true
feature: Journeys
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---


# Guía de [!DNL Journey Orchestration] {#using}

+ [Documentación del producto](journey-orchestration-home.md)
+ Novedades {#release-notes}
   + [Notas de la versión](using/release-notes/release-notes.md)
   + [Actualizaciones de documentación](using/release-notes/documentation-updates.md)
   + [Actualización a Journey Optimizer](using/release-notes/upgrade-to-ajo.md)
+ Primeros pasos con [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Acerca de  [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Limitaciones](using/about/limitations.md)
   + [Introducción ](using/about/get-started.md)
   + [Interfaz de usuario](using/about/user-interface.md)
   + [Administración de acceso](using/about/access-management.md)
   + [Resolución de problemas](using/about/troubleshooting.md)
   + [Integración con sistemas externos](using/about/external-systems.md)
+ Configuración de un evento {#events-journeys}
   + Acerca de los eventos {#about-events}
      + [Principio general](using/event/about-events.md)
      + [Ciclo de datos](using/event/about-data-cycle.md)
      + [Creación de un evento](using/event/about-creating.md)
      + [Aprovechamiento de Adobe Analytics](using/event/about-analytics.md)
      + [Acerca de los esquemas de ExperienceEvent](using/event/experience-event-schema.md)
      + [Pasos adicionales para enviar eventos](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Definición de los campos de carga útil](using/event/defining-the-payload-fields.md)
   + [Selección del área de nombres](using/event/selecting-the-namespace.md)
   + [Definición de la clave del evento](using/event/defining-the-event-key.md)
   + [Previsualización de la carga útil](using/event/previewing-the-payload.md)
+ Configuración de una fuente de datos {#data-source-journeys}
   + [Acerca de las fuentes de datos](using/datasource/about-data-sources.md)
   + [Grupos de campo](using/datasource/field-groups.md)
   + [Fuente de datos de Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Fuentes de datos externas](using/datasource/external-data-sources.md)
+ Configuración de una acción {#action-journeys}
   + [Acerca de las acciones](using/action/action.md)
   + [Uso de Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [Uso de Adobe Campaign v7/v8](using/action/acc-action.md)
   + Uso de un sistema de terceros {#action-third-party}
      + [Acerca de la configuración de acciones personalizadas](using/action/about-custom-action-configuration.md)
      + [Configuración de URL](using/action/url-configuration.md)
      + [Definición de los parámetros del mensaje](using/action/defining-the-message-parameters.md)
+ Uso de segmentos {#configuring-segment}
   + [Acerca de los segmentos](using/segment/about-segments.md)
   + [Creación de segmentos](using/segment/creating-a-segment.md)
   + [Uso de segmentos en condiciones](using/segment/using-a-segment.md)
+ Crear un recorrido {#building-journeys}
   + Acerca de la creación de un recorrido {#about-journey-building}
      + [Creación de un recorrido](using/building-journeys/journey.md)
      + [Uso del diseñador de recorridos](using/building-journeys/using-the-journey-designer.md)
      + [Cambio de las propiedades](using/building-journeys/changing-properties.md)
      + [Versiones de recorridos](using/building-journeys/journey-versions.md)
      + [Finalización de un recorrido](using/building-journeys/terminating-a-journey.md)
      + [Administración de husos horarios](using/building-journeys/timezone-management.md)
      + [Perfiles de prueba](using/building-journeys/creating-test-profiles.md)
   + Actividades {#about-journey-building}
      + Actividades de eventos {#events-activities}
         + [Acerca de las actividades de eventos](using/building-journeys/event-activities.md)
         + [Eventos generales](using/building-journeys/general-events.md)
         + [Eventos de reacción](using/building-journeys/reaction-events.md)
         + [Eventos de cualificación de segmentos](using/building-journeys/segment-qualification-events.md)
      + Actividades de orquestación {#orchestration-activities}
         + [Acerca de las actividades de orquestación](using/building-journeys/about-orchestration-activities.md)
         + [Actividad de condición](using/building-journeys/condition-activity.md)
         + [Actividad final](using/building-journeys/end-activity.md)
         + [Actividad de espera](using/building-journeys/wait-activity.md)
      + Actividades de acción {#action-activities}
         + [Acerca de las actividades de acción](using/building-journeys/about-action-activities.md)
         + [Uso de Adobe Campaign Standard](using/building-journeys/using-adobe-campaign-actions.md)
         + [Uso de Adobe Campaign v7/v8](using/building-journeys/using-adobe-campaign-classic.md)
         + [Uso de acciones personalizadas](using/building-journeys/using-custom-actions.md)
         + [Saltar de un recorrido a otro](using/building-journeys/jump.md)
         + [Actualización de perfil](using/building-journeys/update-profiles.md)
   + [Prueba del recorrido](using/building-journeys/testing-the-journey.md)
   + [Publicación del recorrido](using/building-journeys/publishing-the-journey.md)
   + Uso compartido de los pasos del recorrido con Adobe Experience Platform {#sharing-journey-steps}
      + [Información general sobre el uso compartido de los pasos del recorrido](using/building-journeys/sharing-overview.md)
      + [Lista de campos de eventos de paso](using/building-journeys/sharing-field-list.md)
      + Campos de eventos de paso heredados {#legacy-step-event-fields}
         + [Acerca de los campos heredados](using/building-journeys/sharing-legacy-fields.md)
         + [Campos comunes de los eventos de journeySteps](using/building-journeys/sharing-common-fields.md)
         + [Campos de ejecución de la acción de eventos de journeySteps](using/building-journeys/sharing-execution-fields.md)
         + [Campos de captura de datos de eventos de journeySteps](using/building-journeys/sharing-fetch-fields.md)
         + [Campos de identidad de eventos de journeySteps](using/building-journeys/sharing-identity-fields.md)
         + [campos del recorrido](using/building-journeys/sharing-journey-fields.md)
      + [Ejemplos de consultas](using/building-journeys/query-examples.md)
+ Expresiones de compilación {#building-advanced-conditions-journeys}
   + [Información general](using/expression/expressionadvanced.md)
   + Sintaxis {#syntax}
      + [Generalidades](using/expression/generalities.md)
      + [Instrucción condicional](using/expression/conditional-instruction.md)
      + [Tipos de datos](using/expression/data-types.md)
      + [Referencias del campo](using/expression/field-references.md)
      + [Funciones de administración de colecciones](using/expression/collection-management-functions.md)
      + [Operadores](using/expression/operators.md)
      + [Propiedades del recorrido](using/expression/journey-properties.md)
      + [Ejemplos](using/expression/advanced-editor-use-cases.md)
   + Funciones {#main-functions-journey}
      + [Funciones principales](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Agregación {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [recuento](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversión {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Fecha {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + Lista {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [en](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [límite](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [ordenar](using/functions/functionsort.md)
      + Math {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Cadena {#string}
         + [concatena](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [UUID](using/functions/functionuuid.md)
+ Creación de informes{#journey-reports}
   + [Acerca de los informes de recorrido](using/reporting/about-journey-reports.md)
   + [Creación de informes de recorrido](using/reporting/creating-your-journey-reports.md)
   + [Métricas y dimensiones](using/reporting/metrics-and-dimensions.md)
+ Integración con servicios inteligentes{#use-case-advanced}
   + [Acerca de la integración de inteligencia artificial](using/ai-services/ai-services-overview.md)
   + [Aprovechamiento de la inteligencia artificial aplicada al cliente](using/ai-services/leveraging-customer-ai.md)
+ Casos de uso{#use-cases-journeys}
   + Envío de un correo electrónico personalizado{#use-case-simple}
      + [Acerca del caso de uso simple](using/usecase/about-the-simple-use-case.md)
      + [Configuración del evento](using/usecase/configuring-the-event.md)
      + [Configuración de la fuente de datos](using/usecase/configuring-the-data-source.md)
      + [Construcción del recorrido](using/usecase/simple-uc-building-the-journey.md)
   + Creación de un recorrido en canales múltiples{#use-case-advanced}
      + [Acerca del caso de uso avanzado](using/usecase/about-the-advanced-use-case.md)
      + [Configuración de los eventos](using/usecase/configuring-the-events.md)
      + [Configuración de las fuentes de datos](using/usecase/configuring-the-data-sources.md)
      + [Construcción del recorrido](using/usecase/building-the-journey.md)
   + [Envío de un mensaje mediante Campaign v7/v8](using/usecase/campaign-classic-use-case.md)
   + [Paso de colecciones de forma dinámica mediante acciones personalizadas](using/usecase/collections.md)
+ Uso de API{#working-with-apis}
   + [Introducción a las API de recorridos](using/api/journeys-apis.md)
   + [API de límite](using/api/capping.md)
   + [API de limitación](using/api/throttling.md)
