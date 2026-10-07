---
product: adobe campaign
title: updateTimeZone
description: Obtenga información acerca de la función updateTimeZone
feature: Journeys
role: Developer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 10%
---
# updateTimeZone {#updateTimeZone}

Devuelve una nueva fecha y hora, con una nueva zona horaria en el mismo instante.

## Categoría

Fecha

## Sintaxis de función

`updateTimeZone(<parameters>)`

## Parámetros

* id de zona horaria: cadena
* dateTime

## Firma y tipo devuelto

`updateTimeZone(<dateTime>,<timeZone id>)`

Devuelve una fecha y hora.

## Ejemplos

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Devuelve 2019-08-28T17:15:30.123+02:00.

<!--
`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".
-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Si el valor del campo de marca de tiempo es `2021-11-16T16:55:12.939318+01:00`, la función devuelve `2021-11-17T02:55:12.942115+11:00`.
