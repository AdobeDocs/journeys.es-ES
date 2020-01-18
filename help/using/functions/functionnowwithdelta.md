---
title: nowWithDelta
description: Obtenga información sobre la función nowWithDelta
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# nowWithDelta {#nowWithDelta}

Devuelve la fecha y hora actuales, incluido un desplazamiento. Si se especifica un identificador de zona horaria, se aplicará el desplazamiento de zona horaria. Para obtener más información sobre los tipos de datos, consulte [](../expression/data-types.md).

## Categoría

Fecha

## Sintaxis de función

`nowWithDelta(<parameters>)`

## Parámetros

| Parámetro | Descripción |
|--- |--- |
| delta | valor entero positivo o negativo |
| partición de fecha | años, meses, días, horas, minutos o segundos como cadena |
| id de zona horaria | representación de cadena del valor del huso horario. Para obtener más información, consulte [](../expression/data-types.md). La identificación del huso horario debe ser una constante de cadena. No puede ser una referencia de campo ni una expresión. |

## Firmas y tipo devuelto

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Devuelve un valor de dateTime.

## Ejemplos

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Devuelve un valor de dateTime exactamente hace 2 horas.
