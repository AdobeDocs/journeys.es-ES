---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: Obtenga información sobre la función toDuration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# toDuration {#toDuration}

Convierte un valor de argumento en una duración. Para obtener más información sobre los tipos de datos, consulte [esta página](../expression/data-types.md).

## Categoría

Conversión

## Sintaxis de función

`toDuration(<parameter>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| string | formatos basados en el formato de duración ISO-8601 PnDTnHnMn.nS con días considerados exactamente como 24 horas |
| integer | número de milisegundos |

Si expresión de cadena: los formatos aceptados se basan en el formato de duración ISO-8601 PnDTnHnMn.nS con días considerados exactamente como 24 horas.

La cadena inicio con un signo opcional, denotado por el símbolo ASCII negativo o positivo. Si es negativo, se anula todo el período. La letra ASCII &quot;P&quot; es la siguiente en mayúsculas o minúsculas. Hay cuatro secciones, cada una de ellas compuesta por un número y un sufijo. Las secciones tienen sufijos en ASCII de &quot;D&quot;, &quot;H&quot;, &quot;M&quot; y &quot;S&quot; durante días, horas, minutos y segundos, aceptados en mayúsculas o minúsculas. Los sufijos deben aparecer en orden. La letra ASCII &quot;T&quot; debe aparecer antes de la primera incidencia, si la hay, de una hora, minuto o segunda sección. Al menos una de las cuatro secciones debe estar presente, y si está presente &quot;T&quot; debe haber al menos una sección después de la &quot;T&quot;. La parte numérica de cada sección debe constar de uno o más dígitos ASCII. El número puede ir precedido del símbolo ASCII negativo o positivo. El número de días, horas y minutos debe analizarse a lo largo. El número de segundos debe analizarse junto con la fracción opcional. El punto decimal puede ser un punto o una coma. La parte fraccionada puede tener de cero a 9 dígitos.

## Firmas y tipo devuelto

`toDuration(<string>)`

`toDuration(<integer>)`

Devuelve una duración.

## Ejemplos

`toDuration("PT10H")`

Devuelve la duración de 10 horas.

`toDuration("PT4S")`

Devuelve la duración de 4s.

`toDuration(4000)`

Devuelve la duración de 4s.
