---
product: adobe campaign
title: replace
description: Obtenga información acerca de la sustitución de funciones
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
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
source-wordcount: '148'
ht-degree: 12%
---
# replace {#replace}

Reemplaza la primera incidencia que coincida con la cadena de destino por la cadena de reemplazo de la cadena base.

La sustitución se realiza desde el principio de la cadena hasta el final, por ejemplo, si se sustituye &quot;a&quot; por &quot;b&quot; en la cadena &quot;aaa&quot;, el resultado será &quot;ba&quot; en lugar de &quot;ab&quot;.

## Categoría

Cadena

## Sintaxis de función

`replace(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|--------------|
| basar | cadena |
| Target | cadena (RegExp) |
| reemplazo | cadena |

## Firma y tipo devuelto

`replace(<base>,<target>,<replacement>)`

Devolver una cadena.

## Ejemplo 1

`replace("Hello World", "l", "x")`

Devuelve &quot;Mundo Hexlo&quot;.

## Ejemplo 2 {#example_2}

Dado que el parámetro de destino es RegExp, en función de la cadena que desee reemplazar, es posible que tenga que omitir algunos caracteres. Vea el siguiente ejemplo:

* cadena que evaluar: `|OFFER_A|OFFER_B`
* proporcionado por un atributo de perfil `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Cadena que reemplazar: `|OFFER_A`
* Cadena reemplazada por: `''`
* Debe agregar `\\` antes del carácter `|`.

La expresión es:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

La cadena devuelta es: `|OFFER_B`

También puede generar la cadena que desea reemplazar desde un atributo determinado:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
