---
product: adobe campaign
title: toString
description: Obtenga información acerca de la función toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 9%
---
# toString {#toString}

Convierte un valor de argumento en un valor de cadena, según su tipo. Para obtener más información sobre los tipos de datos, consulte [esta página](../expression/data-types.md).

## Categoría

Conversión

## Sintaxis de función

`toString(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| dateTime | convierte la fecha en formato UTC |
| dateTimeOnly | convierte la fecha en formato UTC |
| duration | convertir en el número correspondiente de milisegundos como cadena |
| entero | convierte en una representación de cadena del valor (1 se convierte en &quot;1&quot;) |
| decimal | convierte en una representación de cadena del valor (1,5 se convierte en &quot;1,5&quot;) |
| Booleano | convertir el valor booleano como &quot;true&quot; si es verdadero, como &quot;false&quot; si es falso |

## Firmas y tipo devuelto

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Devolver una cadena.

## Ejemplo

`toString(4)`

Devuelve &quot;4&quot;.
