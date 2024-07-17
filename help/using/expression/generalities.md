---
product: adobe campaign
title: Generalidades
description: Obtenga información sobre las generalidades de expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 3%

---

# Generalidades {#concept_rcy_qj5_dgb}

## Paréntesis y prioridad de expresión{#section_edf_fks_bgb}

Los paréntesis se pueden utilizar para hacer que una expresión compleja sea más legible. _(&lt;expression>)_ es el equivalente de _&lt;expression>_. Los paréntesis también pueden utilizarse para definir el orden de evaluación y la asociatividad.

Las expresiones se evalúan de izquierda a derecha. Se debe aplicar la asociatividad en operadores aritméticos: las multiplicaciones y divisiones tienen prioridad sobre las sumas y las restas. Para imponer un orden específico, se deben añadir paréntesis para delimitar las operaciones. Por ejemplo:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expresión | Evaluación |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; tiene prioridad sobre &#39;+&#39;: 2 * 10 se evalúa → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Los paréntesis cambian la prioridad: (4 + 2) se evalúa → 6</li><li> 10 → 60</li></ul> |

## Distinción de mayúsculas y minúsculas{#section_lrb_xh5_dgb}

Estas son las diferentes reglas de distinción de mayúsculas y minúsculas:

* Todos los operadores (y, o, etc.) debe escribirse en minúsculas. Por ejemplo, _`<expression1>`y`<expression2>`_ son una expresión válida, mientras que la expresión _`<expression1>`Y`<expression2>`_ no lo son.
* Todos los nombres de función distinguen entre mayúsculas y minúsculas. Por ejemplo, _inSegment()_ es válido mientras que la función _INSEGMENT()_ no lo es.
* Las referencias de campo y los valores constantes distinguen entre mayúsculas y minúsculas: no son elementos integrados del lenguaje (a diferencia de operadores y funciones), son creados por el usuario final.

## Tipo de expresión devuelto{#section_gyc_435_53b}

Según el contexto de uso, el editor de expresiones puede devolver valores diferentes.

| Uso del editor de expresiones avanzadas | Tipo de expresión devuelto esperado |
|--- |--- |
| Condición (condición de fuente de datos, condición de fecha) | Booleano |
| Temporizador personalizado | dateTimeOnly |
| Asignación de parámetros de acción | Cualquiera |
