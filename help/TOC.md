---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# Ayuda de orquestación de viajes {#using}

+ [Documentación del producto](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [Notas de la versión](using/release-notes/release-notes.md)
   + [Actualizaciones de documentación](using/release-notes/documentation-updates.md)
+ Comenzar con la orquestación de viajes {#starting-with-journeys}
   + [Acerca de la orquestación de viajes](using/about/about-journey-orchestration.md)
   + [Introducción](using/about/get-started.md)
   + [Interfaz de usuario](using/about/user-interface.md)
   + [Gestión de acceso](using/about/access-management.md)
   + [Resolución de problemas](using/about/troubleshooting.md)
+ Configuración de un evento {#events-journeys}
   + [Acerca de los eventos](using/event/about-events.md)
   + [Definición de los campos de carga útil](using/event/defining-the-payload-fields.md)
   + [Selección del espacio de nombres](using/event/selecting-the-namespace.md)
   + [Definición de la clave del evento](using/event/defining-the-event-key.md)
   + [Adición de una condición](using/event/adding-a-condition.md)
   + [Vista previa de la carga útil](using/event/previewing-the-payload.md)
   + [Pasos adicionales para enviar eventos](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Configuración de un origen de datos {#data-source-journeys}
   + [Acerca de las fuentes de datos](using/datasource/about-data-sources.md)
   + [Grupos de campo](using/datasource/field-groups.md)
   + [Origen de datos de Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Fuentes de datos externas](using/datasource/external-data-sources.md)
+ Configuración de una acción {#action-journeys}
   + [Acerca de las acciones](using/action/action.md)
   + [Uso de Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Uso de un sistema de terceros {#action-third-party}
      + [Acerca de la configuración de acciones personalizadas](using/action/about-custom-action-configuration.md)
      + [Limitaciones de acciones personalizadas](using/action/custom-action-limitations.md)
      + [Configuración de URL](using/action/url-configuration.md)
      + [Definición de los parámetros del mensaje](using/action/defining-the-message-parameters.md)
+ Construir un viaje {#building-journeys}
   + Acerca de la creación de un viaje {#about-journey-building}
      + [Creación de un viaje](using/building-journeys/journey.md)
      + [Uso del diseñador de viajes](using/building-journeys/using-the-journey-designer.md)
      + [Cambio de las propiedades](using/building-journeys/changing-properties.md)
      + [Versiones de viaje](using/building-journeys/journey-versions.md)
      + [Finalización de un viaje](using/building-journeys/terminating-a-journey.md)
      + [Administración de husos horarios](using/building-journeys/timezone-management.md)
   + Actividades {#about-journey-building}
      + [Actividades de eventos](using/building-journeys/event-activities.md)
      + Actividades de orquestación {#orchestration-activities}
         + [Acerca de las actividades de orquestación](using/building-journeys/about-orchestration-activities.md)
         + [Actividad de condición](using/building-journeys/condition-activity.md)
         + [Actividad final](using/building-journeys/end-activity.md)
         + [Actividad de espera](using/building-journeys/wait-activity.md)
      + Actividades de acción {#action-activities}
         + [Acerca de las actividades de acción](using/building-journeys/about-action-activities.md)
         + [Uso de acciones de Adobe Campaign](using/building-journeys/using-adobe-campaign-actions.md)
         + [Uso de acciones personalizadas](using/building-journeys/using-custom-actions.md)
   + [Prueba del viaje](using/building-journeys/testing-the-journey.md)
   + [Publicación del viaje](using/building-journeys/publishing-the-journey.md)
+ Uso del editor de expresiones avanzadas {#building-advanced-conditions-journeys}
   + [Acerca del editor de expresiones avanzadas](using/expression/expressionadvanced.md)
   + Syntax {#syntax}
      + [Generalidades](using/expression/generalities.md)
      + [Instrucción condicional](using/expression/conditional-instruction.md)
      + [Tipos de datos](using/expression/data-types.md)
      + [Referencias de campo](using/expression/field-references.md)
      + [Funciones de administración de colecciones](using/expression/collection-management-functions.md)
      + [Operadores](using/expression/operators.md)
   + Funciones {#main-functions-journey}
      + [Funciones principales](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + Agregación {#aggregation}
         + [promedio](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [clearCount](using/functions/functiondistinctcount.md)
         + [clearCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversión {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Fecha {#date}
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
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
      + List {#list}
         + [distintivo](using/functions/functiondistinct.md)
         + [differentWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [ordenar](using/functions/functionsort.md)
      + Matemáticas {#math}
         + [aleatorio](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Cadena {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [reemplazar](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [superior](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Creación de informes{#journey-reports}
   + [Acerca de los informes de viaje](using/reporting/about-journey-reports.md)
   + [Creación de informes de viaje](using/reporting/creating-your-journey-reports.md)
   + [Métricas y dimensiones](using/reporting/metrics-and-dimensions.md)
+ Ejemplos de uso{#use-cases-journeys}
   + Caso de uso simple{#use-case-simple}
      + [Acerca del caso de uso simple](using/usecase/about-the-simple-use-case.md)
      + [Configuración del evento](using/usecase/configuring-the-event.md)
      + [Configuración del origen de datos](using/usecase/configuring-the-data-source.md)
      + [Construyendo el viaje](using/usecase/simple-uc-building-the-journey.md)
   + Caso de uso avanzado{#use-case-advanced}
      + [Acerca del caso de uso avanzado](using/usecase/about-the-advanced-use-case.md)
      + [Configuración de los eventos](using/usecase/configuring-the-events.md)
      + [Configuración de las fuentes de datos](using/usecase/configuring-the-data-sources.md)
      + [Construyendo el viaje](using/usecase/building-the-journey.md)
   + [Puntuaciones de fatiga de aprovechamiento](using/usecase/leveraging-fatigue-scores.md)

