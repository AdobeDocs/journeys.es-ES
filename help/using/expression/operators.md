---
product: adobe campaign
solution: Journey Orchestration
title: Operadores
description: Obtenga información sobre los operadores en expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---



# Operadores {#concept_wd5_pj5_dgb}

Existen dos tipos de operadores: operadores unarios y operadores binarios. Hay operadores unarios a la izquierda y operadores unarios a la derecha.

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Esta es la lista de operadores admitidos:

## Lógico {#logical}

### y

```
<expression1> and <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben ser booleanos. El resultado es booleano.

Ejemplo:

```
3.14 > 2 and 3.15 < 1
```

### o



```
<expression1> or <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben ser booleanos. El resultado es booleano.

Ejemplo:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> debe ser booleano. El resultado es booleano.

Ejemplo:

```
not 3.15 < 1
```

## Comparación {#comparison}

### es nulo



```
<expression> is null
```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

Ejemplo:

```
@{BarBeacon.location} is null
```

### no es nulo



```
<expression> is not null
```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

Ejemplo:

```
@ is not null
```

### tiene nulo



```
<expression> has null
```

&lt;expression> debe ser una lista. El resultado es booleano.

Es útil para identificar que una lista contiene al menos un valor nulo.

Ejemplo:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben tener el mismo tipo de datos. El resultado es booleano.

Ejemplo:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben tener el mismo tipo de datos. El resultado es booleano.

Ejemplo:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```
42 >= 3.14
```

### &lt;



```
<expression1> < <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```
42 <= 3.14
```

## Aritmética {#arithmetic}

### +



```
<expression1> + <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

&lt;expression2> no debe ser igual a 0 (devuelve 0).

Ejemplo:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```
3 % 2 -- returns 1.
```

## Matemáticas {#math}

### es numérico



```
<expression> is numeric
```

El tipo de la expresión es integer o decimal.

Ejemplo:

```
@ is numeric
```

### is integer



```
<expression> is integer
```

El tipo de la expresión es integer.

Ejemplo:

```
@ is integer
```

### es decimal



```
<expression> is decimal
```

El tipo de expresión es decimal.

Ejemplo:

```
@ is decimal
```

## Cadena {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Concatena dos expresiones.

Una expresión debe ser una cadena encadenada.

Ejemplo:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Fecha {#date}

### +



```
<expression + <duration>
```

Anexe una duración a dateTime, dateTimeOnly o una duración.

Ejemplo:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
