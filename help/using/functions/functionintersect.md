---
product: adobe campaign
title: intersect
description: Obtenga información sobre la intersección de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# intersección{#intersect}

Devuelve los valores comunes de las dos listas de entrada. Si una de las dos listas es nula, devuelve una lista vacía.

## Categoría

Lista

## Sintaxis de función

`intersect(<parameters>)`

## Parámetros

| Parámetro | Tipo |
|-----------|------------------|
| lista 1 | list |
| lista 2 | list |

## Firmas y tipos devueltos

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Devuelve una lista.

## Ejemplos

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Devuelve [&quot;deportes&quot;, &quot;noticias&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Devuelve elementos comunes entre atributos de perfil y una lista determinada de categorías.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Devuelve elementos comunes entre atributos de perfil y un campo de evento determinado.
