---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: Obtenga información sobre la función toString
feature: Recorridos
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

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
| dateTime | convierte la fecha en formato de fecha UTC |
| dateTimeOnly | convierte la fecha en formato de fecha UTC |
| duration | convertir en el número correspondiente de milisegundos como una cadena |
| zona horaria | convertir en la representación de cadena de id de zona horaria (JOD id) |
| integer | se convierte en una representación de cadena del valor (1 se convierte en &quot;1&quot;) |
| decimal | se convierte en una representación de cadena del valor (1,5 se convierte en &quot;1,5&quot;) |
| booleano | convierta el valor booleano en &#39;true&#39; si es &quot;true&quot;, &#39;false&#39; si es &quot;false&quot; |

## Firmas y tipo devuelto

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Devuelve una cadena.

## Ejemplo

`toString(4)`

Devuelve &quot;4&quot;.
