---
product: adobe campaign
title: updateTimeZone
description: Obtenga información sobre la función updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# updateTimeZone {#updateTimeZone}

Devuelve una nueva hora de fecha, con una nueva zona horaria en el mismo instante.

## Categoría

Fecha 

## Sintaxis de función

`updateTimeZone(<parameters>)`

## Parámetros

* id de zona horaria: string
* dateTime

## Firma y tipo devuelto

`updateTimeZone(<dateTime>,<timeZone id>)`

Devuelve una fecha y hora.

## Ejemplos

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Devuelve 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Si el valor del campo de marca de tiempo es `2021-11-16T16:55:12.939318+01:00`, la función devuelve `2021-11-17T02:55:12.942115+11:00`.
