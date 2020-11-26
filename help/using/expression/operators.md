---
product: adobe campaign
solution: Journey Orchestration
title: Operadores
description: Obtenga información sobre los operadores en expresiones avanzadas
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

Esta es la lista de los operadores admitidos:

## Lógico  {#logical}

### y

**Expresión literal**

```<expression1> and <expression2>```

Tanto &lt;expresión1> como &lt;expresión2> deben ser booleanos. El resultado es booleano.

**Ejemplo**

```3.14 > 2 and 3.15 < 1```

### o

**Expresión literal**

```<expression1> or <expression2>```

Tanto &lt;expresión1> como &lt;expresión2> deben ser booleanos. El resultado es booleano.

**Ejemplo**

```3.14 > 2 or 3.15 < 1```

### not

**Expresión literal**

```not <expression>```

&lt;expresión> debe ser booleano. El resultado es booleano.

**Ejemplo**

```not 3.15 < 1```

## Comparación {#comparison}

### es nulo

**Expresión literal**

```<expression> is null```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

**Ejemplo**

```@{BarBeacon.location} is null```

### no es nulo

**Expresión literal**

```<expression> is not null```

El resultado es booleano.

Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.

**Ejemplo**

```@ is not null```

### tiene nulo

**Expresión literal**

```<expression> has null```

&lt;expresión> debe ser una lista. El resultado es booleano.

Resulta útil identificar que una lista contiene al menos un valor nulo.

**Ejemplo**

```["foo", "bar", null] has null``` devuelve true.

```["foo", "bar", ""] has null``` devuelve false porque &quot;&quot; no se considera nulo.

### ==

**Expresión literal**

```<expression1> == <expression2>```

Tanto &lt;expresión1> como &lt;expresión2> deben tener el mismo tipo de datos. El resultado es booleano.

**Ejemplo**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Expresión literal**

```<expression1> != <expression2>```

Tanto &lt;expresión1> como &lt;expresión2> deben tener el mismo tipo de datos. El resultado es booleano.

**Ejemplo**

```3.14 != 42```

```"foo" != "bar"```

### >

**Expresión literal**

```<expression1> > <expression2>```

La fecha y hora se puede comparar con la fecha y hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto integer como decimal pueden compararse con integer o decimal.

Queda prohibida cualquier otra combinación.

El resultado es booleano.

**Ejemplo**

```3.14 > 42```

### >=

**Expresión literal**

```<expression1> >= <expression2>```

La fecha y hora se puede comparar con la fecha y hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto integer como decimal pueden compararse con integer o decimal.

Queda prohibida cualquier otra combinación.

El resultado es booleano.

**Ejemplo**

```42 >= 3.14```

### &lt;

**Expresión literal**

```<expression1> < <expression2>```

La fecha y hora se puede comparar con la fecha y hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto integer como decimal pueden compararse con integer o decimal.

Queda prohibida cualquier otra combinación.

El resultado es booleano.

**Ejemplo**

```42 < 3.14```

### &lt;=

**Expresión literal**

```<expression1> <= <expression2>```

La fecha y hora se puede comparar con la fecha y hora.

Datetimeonly puede compararse con Datetimeonly.

Tanto integer como decimal pueden compararse con integer o decimal.

Queda prohibida cualquier otra combinación.

El resultado es booleano.

**Ejemplo**

```42 <= 3.14```

## Aritmética {#arithmetic}

### +

**Expresión literal**

```<expression1> + <expression2>```

Ambas expresiones deben ser numéricas (entero o decimal).

El resultado también es numérico.

**Ejemplo**

```1 + 2``` devuelve 3

### -

**Expresión literal**

```<expression1> - <expression2>```

Ambas expresiones deben ser numéricas (entero o decimal).

El resultado también es numérico.

**Ejemplo**

```2 - 1``` devuelve 1

### /

**Expresión literal**

```<expression1> / <expression2>```

Ambas expresiones deben ser numéricas (entero o decimal).

El resultado también es numérico.

&lt;expresión2> no debe ser igual a 0 (devuelve 0).

**Ejemplo**

```4 / 2``` devuelve 2

### *

**Expresión literal**

```<expression1> * <expression2>```

Ambas expresiones deben ser numéricas (entero o decimal).

El resultado también es numérico.

**Ejemplo**

```3 * 4``` devuelve 12

### %

**Expresión literal**

```<expression1> % <expression2>```

Ambas expresiones deben ser numéricas (entero o decimal).

El resultado también es numérico.

**Ejemplo**

```3 % 2``` devuelve 1.

## Matemáticas {#math}

### es numérico

**Expresión literal**

```<expression> is numeric```

El tipo de la expresión es entero o decimal.

**Ejemplo**

```@ is numeric```

### is integer

**Expresión literal**

```<expression> is integer```

El tipo de la expresión es un entero.

**Ejemplo**

```@ is integer```

### es decimal

**Expresión literal**

```<expression> is decimal```

El tipo de expresión es decimal.

**Ejemplo**

```@ is decimal```

## Cadena {#string}

### +

**Expresión literal**

```<string> + <expression>```

```<expression> + <string>```

Concatena dos expresiones.

Una expresión debe ser una cadena encadenada.

**Ejemplo**

```"the current time is " + (now())``` devuelve &quot;la hora actual es 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` devuelve &quot;2019-09-23T09:30:06.693Z es la hora actual&quot;

```"a" + "b" + "c" + 1234``` devuelve &quot;abc1234&quot;.

## Fecha {#date}

### +

**Expresión literal**

```<expression + <duration>```

Anexe una duración a dateTime, a dateTimeOnly o a una duración.

**Ejemplo**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` devuelve 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` devuelve 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` devuelve un dateTime (con la zona horaria UTC) una hora después de la hora actual

```toDuration("PT1H") + toDuration("PT1H")``` devuelve PT2H
