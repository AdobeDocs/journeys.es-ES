---
product: adobe campaign
title: intersección
description: Obtenga información sobre la intersección de funciones
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 10%

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

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Devuelve [&quot;deportes&quot;, &quot;noticias&quot;]

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Devuelve elementos comunes entre atributos de perfil y una lista determinada de categorías.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

Devuelve elementos comunes entre atributos de perfil y un campo de evento determinado.