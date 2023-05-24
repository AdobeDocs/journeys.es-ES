---
product: adobe campaign
title: Tipos de datos
description: Obtenga información sobre los tipos de datos en expresiones avanzadas
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 6%

---

# Tipos de datos {#concept_gp3_rj5_dgb}

Técnicamente, una constante siempre contiene un tipo de datos. En la expresión literal, solo se especifica el valor. El tipo de datos se puede inferir del valor (por ejemplo, cadena, entero, decimal, etc.). Para casos específicos como la fecha y la hora, utilizamos funciones dedicadas para la representación.

Las secciones siguientes proporcionan información sobre las diferentes expresiones de tipo de datos y cómo se representan.

## string {#string}

**Descripción**

Secuencia común de caracteres. No tiene ningún tamaño específico, excepto el implícito que proviene del entorno, como la cantidad de memoria disponible.

Formato JSON: String

Formato de serialización: UTF-8

**Representación literal**

```json
"<value>"
```

```json
'<value>'
```

**Ejemplo**

```json
"hello world"
```

```json
'hello world'
```

## entero {#integer}

**Descripción**

Valor entero entre -2^63 y 2^63-1.

Formato JSON: número

**Representación literal**

```json
<integer value>
```

**Ejemplo**

```json
42
```

## decimal {#decimal}

**Descripción**

Número decimal. Representa un valor flotante:

* mayor valor finito positivo de tipo doble, (2-2^-52)x2^1023
* el menor valor normal positivo del tipo doble, 2-1022
* el menor valor positivo distinto de cero del tipo double, 2 p-1074

Formato JSON: número

Formato de serialización: usando &#39;.&#39; como separador decimal.

**Representación literal**

```json
<integer value>.<integer value>
```

**Ejemplo**

```json
3.14
```

## Booleano {#boolean}

**Descripción**

Valor booleano escrito en minúsculas: true o false

Formato JSON: booleano

**Representación literal**

```json
true
```

```json
false
```

**Ejemplo**

```json
true
```

## dateOnly {#date-only}

**Descripción**

Representa solo una fecha sin una zona horaria, vista como un año-mes-día.

Es una descripción de la fecha, tal como se utiliza para los cumpleaños.

Formato JSON: String.

El formato es: AAAA-MM-DD (ISO-8601), por ejemplo: &quot;2021-03-11&quot;.

Se puede encapsular en una función toDateOnly.

Utiliza DateTimeFormatter ISO_LOCAL_DATE_TIME para deserializar y serializar el valor. [Más información](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Representación literal**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Ejemplo**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Descripción**

Representa una fecha y hora sin una zona horaria, vista como año-mes-día-hora-minuto-segundo-milisegundo.

Formato JSON: String.

No almacena ni representa una zona horaria. En su lugar, es una descripción de la fecha, como se utiliza para los cumpleaños, combinada con la hora local, como se ve en un reloj de pared.

No puede representar un instante en la línea de tiempo sin información adicional, como un desplazamiento o una zona horaria.

Se puede encapsular en una función toDateTimeOnly.

Formato de serialización: formato de fecha y hora de desplazamiento extendido ISO-8601.

Utiliza DateTimeFormatter ISO_LOCAL_DATE_TIME para deserializar y serializar el valor. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Representación literal**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Ejemplos**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Descripción**

Constante de fecha y hora que también considera la zona horaria. Representa una fecha y hora con un desplazamiento con respecto a UTC.

Se puede ver como un instante en el tiempo con la información adicional del offset. Es una manera de representar un &quot;momento&quot; específico en un determinado lugar del mundo.

Formato JSON: String.

Se puede encapsular en una función toDateTime.

Formato de serialización: formato de fecha y hora de desplazamiento extendido ISO-8601.

Utiliza DateTimeFormatter ISO_OFFSET_DATE_TIME para deserializar y serializar el valor. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

También puede pasar un entero que pase un valor epoch. [Más información](https://www.epochconverter.com)

La zona horaria se puede especificar mediante un desplazamiento o un código de zona horaria (por ejemplo: Europa/París, Z - que significa UTC).

**Representación literal**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Ejemplos**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## duration {#duration}

**Descripción**

Representa una cantidad de tiempo basada en el tiempo, como &quot;34,5 segundos&quot;. Modela una cantidad o cantidad de tiempo en términos de milisegundos.

Las unidades temporales admitidas son: milisegundos, segundos, minutos, horas, días en los que un día es igual a 24 horas. No se admiten años y meses porque no son una cantidad de tiempo fija.

Formato JSON: String.

Debe encapsularse en una función toDuration.

Formato de serialización: para deserializar un ID de zona horaria, se utiliza la función java java.time.

Duration.parse: los formatos aceptados se basan en el formato de duración ISO-8601 PnDTnHnMn.nS con días considerados exactamente 24 horas. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Representación literal**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Ejemplo**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Descripción**

Lista separada por comas de expresiones con corchetes como delimitadores.

No se admite el polimorfismo, por lo que todas las expresiones contenidas en la lista deben tener el mismo tipo.

**Representación literal**

```json
[<expression>, <expression>, ... ]
```

**Ejemplo**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
