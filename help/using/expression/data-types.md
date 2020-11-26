---
product: adobe campaign
solution: Journey Orchestration
title: Tipos de datos
description: Obtenga información sobre los tipos de datos en expresiones avanzadas
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 5%

---


# Tipos de datos {#concept_gp3_rj5_dgb}

Técnicamente, una constante siempre contiene un tipo de datos. En la expresión literal, solo especificamos el valor. El tipo de datos se puede inferir del valor (por ejemplo, cadena, entero, decimal, etc.). Para casos específicos como la fecha y hora, utilizamos funciones específicas para la representación.

Las secciones siguientes proporcionan información sobre las diferentes expresiones de tipo de datos y cómo se representan.

## string {#string}

**Descripción**

Secuencia común de caracteres. No tiene ningún tamaño específico excepto el implícito que viene del entorno, como la cantidad de memoria disponible.

Formato JSON: Cadena

Formato de serialización: UTF-8

**Representación literaria**

```
"<value>"
```

```
'<value>'
```

**Ejemplo**

```
"hello world"
```

```
'hello world'
```

## integer {#integer}

**Descripción**

Valor entero de -2^63 a 2^63-1.

Formato JSON: Número

**Representación literaria**

```
<integer value>
```

**Ejemplo**

```
42
```

## decimal {#decimal}

**Descripción**

Número decimal. Representa un valor flotante:

* valor finito más alto del tipo doble, (2-2^-52)x2^1023
* valor normal positivo más pequeño del tipo doble, 2-1022
* valor nulo positivo más pequeño del tipo doble, 2 p-1074

Formato JSON: Número

Formato de serialización: usando &#39;.&#39; como separador decimal.

**Representación literaria**

```
<integer value>.<integer value>
```

**Ejemplo**

```
3.14
```

## booleano {#boolean}

**Descripción**

Valor booleano escrito en minúsculas: true o false

Formato JSON: Booleano

**Representación literaria**

```
true
```

```
false
```

**Ejemplo**

```
true
```

## dateTimeOnly {#date-time-only}

**Descripción**

Representa una fecha y hora sin zona horaria, vista como año-mes-día-hora-minuto-segundo-milisegundo.

No almacena ni representa un huso horario. En cambio, es una descripción de la fecha, como se usa para los cumpleaños, combinada con la hora local como se ve en un reloj de pared.

No puede representar un instante en la línea de tiempo sin información adicional como un desplazamiento o una zona horaria.

Formato de serialización: Formato de fecha y hora de desplazamiento ampliado ISO-8601.

Utiliza DateTimeFormateria ISO_LOCAL_DATE_TIME para deserializar y serializar el valor. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Representación literaria**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**Descripción**

Constante de fecha y hora que también tiene en cuenta la zona horaria. Representa una fecha y hora con un desplazamiento de UTC.

Se puede ver como un instante en el tiempo con la información adicional del desplazamiento. Es una manera de representar un &quot;momento&quot; específico en un determinado lugar del mundo.

Formato JSON: Cadena.

Debe encapsularse en una función toDateTime.

Formato de serialización: Formato de fecha y hora de desplazamiento ampliado ISO-8601.

Utiliza DateTimeFormateria ISO_OFFSET_DATE_TIME para deserializar y serializar el valor. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

También puede pasar un entero que pase un valor epoch. [Más información](https://www.epochconverter.com)

La zona horaria se puede especificar mediante un desplazamiento o un código de zona horaria (ejemplo: Europa/París, Z (es decir, UTC).

**Representación literaria**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**Ejemplo**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## duration {#duration}

**Descripción**

Representa una cantidad de tiempo basada en el tiempo, como &quot;34,5 segundos&quot;. Modela una cantidad o cantidad de tiempo en milisegundos.

Las unidades temporales admitidas son: milisegundos, segundos, minutos, horas, días en los que un día equivale a 24 horas. No se admiten años y meses porque no son una cantidad de tiempo fija.

Formato JSON: Cadena.

Debe encapsularse en una función toDuration.

Formato de serialización: Para deserializar un ID de zona horaria, utiliza la función java java.time.

Duration.parse: los formatos aceptados se basan en el formato de duración ISO-8601 PnDTnHnMn.nS con días considerados exactamente como 24 horas. [Más información](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Representación literaria**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**Ejemplo**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## lista {#list}

**Descripción**

Lista separada por comas de expresiones utilizando corchetes como delimitadores.

No se admite el polimorfismo, por lo que todas las expresiones contenidas en la lista deben tener el mismo tipo.

**Representación literaria**

```
[<expression>, <expression>, ... ]
```

**Ejemplo**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
