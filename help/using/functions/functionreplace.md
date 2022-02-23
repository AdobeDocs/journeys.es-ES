---
product: adobe campaign
title: replace
description: Obtenga información sobre la sustitución de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 10%

---

# replace {#replace}

Reemplaza la primera incidencia que coincide con la cadena de destino por la cadena de reemplazo de la cadena base.

La sustitución procede desde el principio de la cadena hasta el final, por ejemplo, reemplazar &quot;aa&quot; por &quot;b&quot; en la cadena &quot;aaa&quot; resultará en &quot;ba&quot; en lugar de &quot;ab&quot;.

## Categoría

Cadena

## Sintaxis de función

`replace(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|--------------|
| base | string |
| Target | string (RegExp) |
| reemplazo | string |

## Firma y tipo devuelto

`replace(<base>,<target>,<replacement>)`

Devuelve una cadena.

## Ejemplo 1

`replace("Hello World", "l", "x")`

Devuelve &quot;Hexlo World&quot;.

## Ejemplo 2 {#example_2}

Como el parámetro de destino es un RegExp, según la cadena que desee reemplazar, es posible que tenga que escapar algunos caracteres. Vea el siguiente ejemplo:

* cadena que se va a evaluar: `|OFFER_A|OFFER_B`
* proporcionado por un atributo de perfil `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Cadena que se va a reemplazar: `|OFFER_A`
* Cadena reemplazada por: `''`
* Debe añadir `\\` antes de que `|` carácter.

La expresión es:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

La cadena devuelta es: `|OFFER_B`

También puede crear la cadena que desea reemplazar desde un atributo determinado:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
