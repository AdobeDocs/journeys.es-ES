---
title: inNextYears
description: Obtenga información sobre la función en NextYears
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
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49

---


# inNextYears {#inNextYears}

Devuelve true si una fecha o fechaTime dada está entre ahora y ahora + años delta.

## Categoría

Fecha

## Sintaxis de función

`inNextYears(<dateTime>,<delta>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| fecha y hora | dateTime |
| delta | integer |

## Firmas y tipo devuelto

`inNextYears(<dateTime>,<integer>)`

Devuelve un valor booleano.

## Ejemplos

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Devuelve true.
