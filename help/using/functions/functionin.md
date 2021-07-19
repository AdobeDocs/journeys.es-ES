---
product: adobe campaign
title: en
description: Obtenga información sobre la función en
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 17%

---

# en {#in}

Comprueba si el primer valor de argumento está en la lista. La comprobación se realiza mediante un valor Equal en cada valor de argumento. Devuelve true si se encuentra el valor del argumento, false en caso contrario.

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
| Número entero | Número entero |
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

Devuelve un booleano.

## Ejemplo

`in(4,[4,5,3,4])`

Devuelve verdadero.

`in(8,[4,5,3,4])`

Devuelve falso.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
