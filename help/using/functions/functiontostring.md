---
product: adobe campaign
title: toString
description: Obtenga información acerca de la función toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
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
