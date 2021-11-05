---
product: adobe campaign
title: Operadores
description: Obtenga información sobre los operadores en expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---

# Operadores {#concept_wd5_pj5_dgb}

Existen dos tipos de operadores: operadores unarios y operadores binarios. Hay operadores unarios a la izquierda y operadores unarios a la derecha.

```json
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

## Lógica  {#logical}

### y

```json
<expression1> and <expression2>
```

Ambas &lt;expression1> y &lt;expression2> debe ser booleano. El resultado es booleano.

Ejemplo:

```json
3.14 > 2 and 3.15 < 1
```

### o



```json
<expression1> or <expression2>
```

Ambas &lt;expression1> y &lt;expression2> debe ser booleano. El resultado es booleano.

Ejemplo:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> debe ser booleano. El resultado es booleano.

Ejemplo:

```json
not 3.15 < 1
```

## Comparación {#comparison}

### es nulo



```json
<expression> is null
```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

Ejemplo:

```json
@{BarBeacon.location} is null
```

### no es nulo



```json
<expression> is not null
```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

Ejemplo:

```json
@ is not null
```

### tiene nulo



```json
<expression> has null
```

&lt;expression> debe ser una lista. El resultado es booleano.

Es útil para identificar que una lista contiene al menos un valor nulo.

Ejemplo:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Ambas &lt;expression1> y &lt;expression2> debe tener el mismo tipo de datos. El resultado es booleano.

Ejemplo:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Ambas &lt;expression1> y &lt;expression2> debe tener el mismo tipo de datos. El resultado es booleano.

Ejemplo:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

La fecha y la hora se pueden comparar con la fecha y la hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto el entero como el decimal se pueden comparar con el entero o con el decimal.

Se prohíbe cualquier otra combinación.

El resultado es booleano.

Ejemplo:

```json
42 <= 3.14
```

## Aritmética {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

&lt;expression2> no debe ser igual a 0 (devuelve 0).

Ejemplo:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Ambas expresiones deben ser numéricas (números enteros o decimales).

El resultado también es numérico.

Ejemplo:

```json
3 % 2 -- returns 1.
```

## Math {#math}

### es numérico



```json
<expression> is numeric
```

El tipo de la expresión es integer o decimal.

Ejemplo:

```json
@ is numeric
```

### is integer



```json
<expression> is integer
```

El tipo de la expresión es integer.

Ejemplo:

```json
@ is integer
```

### es decimal



```json
<expression> is decimal
```

El tipo de expresión es decimal.

Ejemplo:

```json
@ is decimal
```

## Cadena {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Concatena dos expresiones.

Una expresión debe ser una cadena encadenada.

Ejemplo:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Fecha  {#date}

### +



```json
<expression> + <duration>
```

Anexe una duración a dateTime, dateTimeOnly o una duración.

Ejemplo:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
