---
product: adobe campaign
title: updateTimeZone
description: Obtenga información sobre la función updateTimeZone
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

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

## Ejemplo

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Devuelve 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
