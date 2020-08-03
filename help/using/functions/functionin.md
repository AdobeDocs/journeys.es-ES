---
title: in
description: Obtenga información sobre la función en
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 12%

---


# in {#in}

Comprueba si el primer valor de argumento está en la lista. La comprobación se realiza mediante un valor de igual en cada valor de argumento. Devuelve true si se encuentra el valor del argumento; en caso contrario, false.

El tipo de `<expression>` debe coincidir con los elementos de la lista. Los tipos de elementos de la lista, como recordatorio, deben coincidir entre sí.

## Categoría

Lista

## Sintaxis de función

`in(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| Cadena | Cadena |
| Booleano | Booleano |
| Entero | Entero |
| Decimal | Decimal |
| Duración | Duración |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Firma y tipo devuelto

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Devolver un booleano.

## Ejemplo

`in(4,[4,5,3,4])`

Devuelve true.

`in(8,[4,5,3,4])`

Devuelve false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
