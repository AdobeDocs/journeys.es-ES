---
product: adobe campaign
solution: Journey Orchestration
title: Funciones
description: Obtenga información sobre las funciones
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 71%

---


# Funciones {#concept_p1r_qj5_dgb}

Una función puede tener firmas diferentes (un conjunto diferente de parámetros ordenados). Una firma de función puede tener expresiones 0-N como parámetros ordenados.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Cada función tiene un tipo específico devuelto.

Esta es la lista de funciones compatibles.

## Funciones principales

| Categoría | Función |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Agregación | [avg](../functions/functionavg.md) |
| Agregación | [count](../functions/functioncount.md) |
| Agregación | [countOnlyNull](../functions/functioncountonlynull.md) |
| Agregación | [countWithNull](../functions/functioncountwithnull.md) |
| Agregación | [distinctCount](../functions/functiondistinctcount.md) |
| Agregación | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Agregación | [max](../functions/functionmax.md) |
| Agregación | [min](../functions/functionmin.md) |
| Agregación | [sum](../functions/functionsum.md) |
| Conversión | [toBool](../functions/functiontobool.md) |
| Conversión | [toDateTime](../functions/functiontodatetime.md) |
| Conversión | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Conversión | [toDecimal](../functions/functiontodecimal.md) |
| Conversión | [toDuration](../functions/functiontoduration.md) |
| Conversión | [toInteger](../functions/functiontointeger.md) |
| Conversión | [toString](../functions/functiontostring.md) |
| Fecha | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Fecha | [inLastDays](../functions/functioninlastdays.md) |
| Fecha | [inLastHours](../functions/functioninlasthours.md) |
| Fecha | [inLastMonths](../functions/functioninlastmonths.md) |
| Fecha | [inLastYears](../functions/functioninlastyears.md) |
| Fecha | [inNextDays](../functions/functioninnextdays.md) |
| Fecha | [inNextHours](../functions/functioninnexthours.md) |
| Fecha | [inNextMonths](../functions/functioninnextmonths.md) |
| Fecha | [inNextYears](../functions/functioninnextyears.md) |
| Fecha | [now](../functions/functionnow.md) |
| Fecha | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Fecha | [setHours](../functions/functionsethours.md) |
| Fecha | [setDays](../functions/functionsetdays.md) |
| Lista | [distinct](../functions/functiondistinct.md) |
| Lista | [distinctCount](../functions/functiondistinctcount.md) |
| Lista | [in](../functions/functionin.md) |
| Lista | [listSize](../functions/functionlistsize.md) |
| Lista | [serializeList](../functions/functionserializelist.md) |
| Lista | [sort](../functions/functionsort.md) |
| Matemáticas | [random](../functions/functionrandom.md) |
| Matemáticas | [round](../functions/functionround.md) |
| Cadena | [concat](../functions/functionconcat.md) |
| Cadena | [contain](../functions/functioncontain.md) |
| Cadena | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Cadena | [endWith](../functions/functionendwith.md) |
| Cadena | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Cadena | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Cadena | [indexOf](../functions/functionindexof.md) |
| Cadena | [isEmpty](../functions/functionisempty.md) |
| Cadena | [isNotEmpty](../functions/functionisnotempty.md) |
| Cadena | [lastIndexOf](../functions/functionlastindexof.md) |
| Cadena | [length](../functions/functionlength.md) |
| Cadena | [lower](../functions/functionlower.md) |
| Cadena | [matchRegExp](../functions/functionmatchregexp.md) |
| Cadena | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Cadena | [replace](../functions/functionreplace.md) |
| Cadena | [replaceAll](../functions/functionreplaceall.md) |
| Cadena | [startWith](../functions/functionstartwith.md) |
| Cadena | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Cadena | [substr](../functions/functionsubstr.md) |
| Cadena | [trim](../functions/functiontrim.md) |
| Cadena | [upper](../functions/functionupper.md) |
| Cadena | [uuid](../functions/functionuuid.md) |