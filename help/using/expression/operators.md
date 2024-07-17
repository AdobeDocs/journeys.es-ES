---
product: adobe campaign
title: Operadores
description: Obtenga información sobre los operadores en expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# Operadores {#concept_wd5_pj5_dgb}

Existen dos tipos de operadores: operadores unarios y operadores binarios. Hay operadores unarios de la izquierda y operadores unarios de la derecha.

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

## Notas importantes{#important-notes}

* Al utilizar una multiplicación (`*`), ambos campos de operación deben tener el mismo tipo, ya sea entero o decimal. Ejemplo :
   * el siguiente ejemplo es correcto: `3.0 * 4.0`
   * `3 * 4.0` generará un error

## Lógico  {#logical}

### y

```json
<expression1> and <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben ser booleanas. El resultado es booleano.

Por ejemplo:

```json
3.14 > 2 and 3.15 < 1
```

### o



```json
<expression1> or <expression2>
```

Tanto &lt;expression1> como &lt;expression2> deben ser booleanas. El resultado es booleano.

Por ejemplo:

```json
3.14 > 2 or 3.15 < 1
```

### no



```json
not <expression>
```

&lt;expression> debe ser booleano. El resultado es booleano.

Por ejemplo:

```json
not 3.15 < 1
```

## Comparación {#comparison}

### es nulo



```json
<expression> is null
```

El resultado es booleano.

Tenga en cuenta que nulo significa que la expresión no tiene ningún valor evaluado.

Por ejemplo:

```json
@{BarBeacon.location} is null
```

### no es nulo



```json
<expression> is not null
```

El resultado es booleano.

Tenga en cuenta que nulo significa que la expresión no tiene ningún valor evaluado.

Por ejemplo:

```json
@ is not null
```

### tiene null



```json
<expression> has null
```

&lt;expression> debe ser una lista. El resultado es booleano.

Resulta útil para identificar que una lista contiene al menos un valor nulo.

Por ejemplo:

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

Tanto &lt;expression1> como &lt;expression2> deben tener el mismo tipo de datos. El resultado es booleano.

Por ejemplo:

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

Tanto &lt;expression1> como &lt;expression2> deben tener el mismo tipo de datos. El resultado es booleano.

Por ejemplo:

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

Datetime se puede comparar con Datetime.

Datetimeonly se puede comparar con Datetimeonly.

Tanto el entero como el decimal pueden compararse con ambos valores, entero o decimal.

Cualquier otra combinación está prohibida.

El resultado es booleano.

Por ejemplo:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime se puede comparar con Datetime.

Datetimeonly se puede comparar con Datetimeonly.

Tanto el entero como el decimal pueden compararse con ambos valores, entero o decimal.

Cualquier otra combinación está prohibida.

El resultado es booleano.

Por ejemplo:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime se puede comparar con Datetime.

Datetimeonly se puede comparar con Datetimeonly.

Tanto el entero como el decimal pueden compararse con ambos valores, entero o decimal.

Cualquier otra combinación está prohibida.

El resultado es booleano.

Por ejemplo:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime se puede comparar con Datetime.

Datetimeonly se puede comparar con Datetimeonly.

Tanto el entero como el decimal pueden compararse con ambos valores, entero o decimal.

Cualquier otra combinación está prohibida.

El resultado es booleano.

Por ejemplo:

```json
42 <= 3.14
```

## Aritmética {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Ambas expresiones deben ser numéricas (enteras o decimales).

El resultado también es numérico.

Por ejemplo:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Ambas expresiones deben ser numéricas (enteras o decimales).

El resultado también es numérico.

Por ejemplo:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Ambas expresiones deben ser numéricas (enteras o decimales).

El resultado también es numérico.

&lt;expression2> no debe ser igual a 0 (devuelve 0).

Por ejemplo:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Ambas expresiones deben ser numéricas (enteras o decimales).

El resultado también es numérico.

Por ejemplo:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Ambas expresiones deben ser numéricas (enteras o decimales).

El resultado también es numérico.

Por ejemplo:

```json
3 % 2 -- returns 1.
```

## Matemáticas {#math}

### es numérico



```json
<expression> is numeric
```

El tipo de expresión es entero o decimal.

Por ejemplo:

```json
@ is numeric
```

### es entero



```json
<expression> is integer
```

El tipo de expresión es entero.

Por ejemplo:

```json
@ is integer
```

### es decimal



```json
<expression> is decimal
```

El tipo de expresión es decimal.

Por ejemplo:

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

Por ejemplo:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Fecha {#date}

### +



```json
<expression> + <duration>
```

Anexe una duración a dateTime, dateTimeOnly o duration.

Por ejemplo:

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
