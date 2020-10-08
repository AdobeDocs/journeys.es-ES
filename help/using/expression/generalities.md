---
title: Generalidades
description: Obtenga información sobre las generalidades de expresión avanzada
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Generalidades {#concept_rcy_qj5_dgb}

## Paréntesis y prioridad de expresión{#section_edf_fks_bgb}

Los paréntesis se pueden utilizar para que una expresión compleja sea más legible. _(&lt;expresión>)_ es el equivalente de _&lt;expresión>_. Los paréntesis también se pueden utilizar para definir el orden de evaluación y la asociatividad.

Las expresiones se evaluarán de izquierda a derecha. La asociatividad de los operadores aritméticos debe aplicarse: las multiplicaciones y las divisiones tienen prioridad sobre las adiciones y las sustracciones. Para imponer un orden específico, se deben añadir paréntesis para delimitar las operaciones. Por ejemplo:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expresión | Evaluación |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; tiene prioridad sobre &#39;+&#39;: 2 * 10 se evalúa → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Los paréntesis cambian la prioridad: (4 + 2) se evalúa → 6</li><li> 6 * 10 → 60</li></ul> |

## Case sensitivity{#section_lrb_xh5_dgb}

Estas son las distintas reglas de distinción de mayúsculas y minúsculas:

* Todos los operadores (y, o, etc.) debe escribirse en minúsculas. Por ejemplo, _`<expression1>`y`<expression2>`_ es una expresión válida, mientras que la expresión _`<expression1>`Y`<expression2>`_ no lo es.
* Todos los nombres de funciones distinguen entre mayúsculas y minúsculas. Por ejemplo, _inSegment()_ es válido, mientras que la función _INSEGMENT()_ no lo es.
* Las referencias de campo y los valores constantes distinguen entre mayúsculas y minúsculas: no son elementos integrados del idioma (a diferencia de los operadores y las funciones), son creados por el usuario final.

## Tipo de expresión devuelta{#section_gyc_435_53b}

Según el contexto de uso, el editor de expresiones puede devolver valores diferentes.

| Uso avanzado del editor de expresiones | Tipo de expresión devuelto esperado |
|--- |--- |
| Condición (condición de fuente de datos, condición de fecha) | booleano |
| Temporizador personalizado | dateTimeOnly |
| Asignación de parámetros de acción | Cualquiera |
