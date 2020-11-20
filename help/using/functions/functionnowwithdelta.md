---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Obtenga información sobre la función nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

Devuelve la fecha y hora actuales, incluido un desplazamiento. Si se especifica un identificador de zona horaria, se aplicará el desplazamiento de zona horaria. For more information on data types, refer to [this page](../expression/data-types.md).

## Categoría

Fecha

## Sintaxis de función

`nowWithDelta(<parameters>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| delta | valor entero positivo o negativo |
| partición de fecha | años, meses, días, horas, minutos o segundos como cadena |
| id de zona horaria | representación de cadena del valor del huso horario. Para obtener más información, consulte Tipos [de datos](../expression/data-types.md). La identificación del huso horario debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión. |

## Firmas y tipo devuelto

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Devuelve un valor de dateTime.

## Ejemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Devuelve un valor de dateTime exactamente hace 2 horas.
