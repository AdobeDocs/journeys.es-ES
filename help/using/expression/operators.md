---
title: Operadores
description: Obtenga información sobre los operadores en expresiones avanzadas
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
source-wordcount: '618'
ht-degree: 4%

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

## Lógico

<table>
<thead>
<tr ><th  >Operador</th><th  >Expresión literal</th><th  >Ejemplo</th></tr>
</thead>
<tbody>
<tr >&gt;<td>y</td><td><p><pre>&lt;expresión1&gt; y &lt;expresión2&gt;</pre></p>Tanto &lt;expresión1&gt; como &lt;expresión2&gt; deben ser booleanos. El resultado es booleano.</td><td><pre>3.14 &gt; 2 y 3.15 &lt; 1</pre></td></tr>
<tr ><td>o</td><td><p><pre>&lt;expresión1&gt; o &lt;expresión2&gt;</pre></p><p>Tanto &lt;expresión1&gt; como &lt;expresión2&gt; deben ser booleanos.</p><p> El resultado es booleano.</p></td><td><p><pre>3.14 &gt; 2 o 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>no &lt;expresión&gt;</pre></p><p>&lt;expresión&gt; debe ser booleano.</p><p> El resultado es booleano.</p></td><td><pre>no 3,15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Comparación

<table>
<thead>
<tr ><th  >Operador</th><th  >Expresión literal </th><th  >Ejemplo</th></tr>
</thead>
<tbody><tr ><td>es nulo</td><td><p><pre>&lt;expresión&gt; es nulo</pre></p><p>El resultado es booleano.</p><p>Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.</p></td><td><pre>@{BarBeacon.location} es nulo</pre></td></tr>
<tr ><td>no es nulo</td><td><p><pre>&lt;expresión&gt; no es nulo</pre></p><p>El resultado es booleano.</p><p>Tenga en cuenta que null significa que la expresión no tiene ningún valor evaluado.</p></td><td><pre>@ no es nulo</pre></td></tr>
<tr ><td>tiene nulo</td><td><p><pre>&lt;expresión&gt; tiene nulo</pre>&lt;expresión&gt; debe ser una lista.</p><p>El resultado es booleano.</p><p>Resulta útil identificar que una lista contiene al menos un valor nulo.</p></td><td><p><pre>["foo", "bar", nulo] tiene nulo</pre></p>devuelve true<p><pre>["foo", "bar", ""] tiene nulo</pre></p> devuelve false porque "" no se considera nulo.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expresión1&gt; == &lt;expresión2&gt;</pre></p><p>Tanto &lt;expresión1&gt; como &lt;expresión2&gt; deben tener el mismo tipo de datos.</p><p> El resultado es booleano.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expresión1&gt; != &lt;expresión2&gt;</pre></p><p> Tanto &lt;expresión1&gt; como &lt;expresión2&gt; deben tener el mismo tipo de datos.</p><p> El resultado es booleano.</p></td><td><pre>3.14 != 42</pre><br /><pre>¡"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expresión1&gt; &gt; &lt;expresión2&gt;</pre></p><p>La fecha y hora se puede comparar con la fecha y hora.</p><p>Datetimeonly puede compararse con Datetimeonly.</p><p>Tanto integer como decimal pueden compararse con integer o decimal.</p><p>Queda prohibida cualquier otra combinación.</p><p>El resultado es booleano.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expresión1&gt; &gt;= &lt;expresión2&gt;</pre></p><p>La fecha y hora se puede comparar con la fecha y hora.</p><p>Datetimeonly puede compararse con Datetimeonly.</p><p>Tanto integer como decimal pueden compararse con integer o decimal.</p><p>Queda prohibida cualquier otra combinación.</p><p>El resultado es booleano.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expresión1&gt; &lt; &lt;expresión2&gt;</pre></p><p>La fecha y hora se puede comparar con la fecha y hora.</p><p>Datetimeonly puede compararse con Datetimeonly.</p><p>Tanto integer como decimal pueden compararse con integer o decimal.</p><p>Queda prohibida cualquier otra combinación.</p><p>El resultado es booleano.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expresión1&gt; &lt;= &lt;expresión2&gt;</pre></p><p>La fecha y hora se puede comparar con la fecha y hora.</p><p>Datetimeonly puede compararse con Datetimeonly.</p><p>Tanto integer como decimal pueden compararse con integer o decimal.</p><p>Queda prohibida cualquier otra combinación.</p><p>El resultado es booleano.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Aritmética

<table>
<thead>
<tr ><th  >Operador</th><th>Expresión literal </th><th  >Ejemplo</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expresión1&gt; + &lt;expresión2&gt;</pre></p><p>Ambas expresiones deben ser numéricas (entero o decimal). </p><p>El resultado también es numérico.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Devuelve 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expresión1&gt; - &lt;expresión2&gt;</pre></p><p> Ambas expresiones deben ser numéricas (entero o decimal).</p><p> El resultado también es numérico.</p></td><td><p><pre>2 - 1</pre></p>Devuelve 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expresión1&gt; / &lt;expresión2&gt;</pre></p><p>Ambas expresiones deben ser numéricas (entero o decimal). </p><p>El resultado también es numérico.</p><p>&lt;expresión2&gt; no debe ser igual a 0 (devuelve 0).</p></td><td><p><pre>4 / 2</pre></p>Devuelve 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expresión1&gt; * &lt;expresión2&gt;</pre></p><p> Ambas expresiones deben ser numéricas (entero o decimal). </p><p>El resultado también es numérico.</p></td><td><p><pre>3 * 4</pre></p>Devuelve 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expresión1&gt; % &lt;expresión2&gt;</pre></p><p>Ambas expresiones deben ser numéricas (entero o decimal).</p><p> El resultado también es numérico.</p></td><td><p><pre>3 % 2</pre></p>Devuelve 1.</td></tr>
</tbody>
</table>

## Matemáticas

<table>
<thead>
<tr ><th  >Operador</th><th  >Expresión literal </th><th  >Ejemplo</th></tr>
</thead>
<tbody><tr ><td>es numérico</td><td><p><pre>&lt;expresión&gt; es numérico</pre></p><p>El tipo de la expresión es entero o decimal.</p></td><td><pre>@ es numérico</pre></td></tr>
<tr ><td>is integer</td><td><p><pre>&lt;expresión&gt; es un entero</pre></p><p>El tipo de la expresión es un entero.</p></td><td><pre>@ es entero</pre></td></tr>
<tr ><td>es decimal</td><td><p><pre>&lt;expresión&gt; es decimal</pre></p><p>El tipo de expresión es decimal.</p></td><td><pre>@ es decimal</pre></td></tr>

## Cadena

<table>
<thead>
<tr ><th  >Operador</th><th  >Expresión literal </th><th  >Ejemplo</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;cadena&gt; + &lt;expresión&gt;</pre></p><p><pre>&lt;expresión&gt; + &lt;cadena&gt;</pre></p><p>Concatena dos expresiones. </p><p>Una expresión debe ser una cadena encadenada.</p></td><td><p><pre>"la hora actual es " + (now()))</pre></p> Devuelve "la hora actual es 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " es la hora actual"</pre></p>Devuelve "2019-09-23T09:30:06.693Z es la hora actual"<p><pre>"a" + "b" + "c" + 1234</pre></p> Devuelve "abc1234".</td></tr>
</tbody>
</table>

## Fecha

<table>
<thead>
<tr ><th  >Operador</th><th  >Expresión literal </th><th  >Ejemplo</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expresión + &lt;duración&gt;</pre></p><p>Anexe una duración a dateTime, a dateTimeOnly o a una duración.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Devuelve 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Devuelve 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Devuelve un valor dateTime (con la zona horaria UTC) una hora después de la hora actual</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Devuelve PT2H</p></td></tr>
</tbody>
</table>