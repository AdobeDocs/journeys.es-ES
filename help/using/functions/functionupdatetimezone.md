---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: Obtenga información sobre la función updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

Devuelve una nueva hora de fecha, con una nueva zona horaria en el mismo instante.

## Categoría

Fecha

## Sintaxis de función

`updateTimeZone(<parameters>)`

## Parámetros

* id. de zona horaria: string
* dateTime

## Firma y tipo devuelto

`updateTimeZone(<dateTime>,<timeZone id>)`

Devuelve una fecha y hora.

## Ejemplo

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Devuelve 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
