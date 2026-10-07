---
product: adobe campaign
title: en
description: Obtenga información acerca de la función en
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
source-wordcount: '113'
ht-degree: 24%
---
# en {#in}

Comprueba si el primer valor del argumento está en la lista. La comprobación se realiza mediante un valor Equal en cada argumento value. Devuelve true si se encuentra el valor del argumento; en caso contrario, devuelve false.

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
| Fecha/Hora | Fecha/Hora |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Firma y tipo devuelto

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Devuelve un valor booleano.

## Ejemplo

`in(4,[4,5,3,4])`

Devuelve verdadero.

`in(8,[4,5,3,4])`

Devuelve falso.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
