---
title: Tipos de datos
description: Obtenga información sobre los tipos de datos en expresiones avanzadas
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c

---


# Tipos de datos {#concept_gp3_rj5_dgb}

Técnicamente, una constante siempre contiene un tipo de datos. En la expresión literal, solo se especifica el valor. El tipo de datos se puede inferir del valor (por ejemplo, cadena, entero, decimal, etc.). Para casos específicos como la fecha y hora, utilizamos funciones específicas para la representación.

A continuación se muestra cómo se representan las expresiones de tipo de datos:

<table>
    <thead>
        <tr>
        <td>Tipo de datos</td>
        <td>Descripción</td>
        <td>Representación literal</td>
        <td>Ejemplo</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Secuencia común de caracteres.</p><p>No tiene ningún tamaño específico excepto el implícito que proviene del entorno, como la cantidad de memoria disponible.</p><p>Formato JSON: Cadena</p><p>Formato de serialización: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hola mundo"</pre></p><p><pre>'hola mundo'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Valor entero de -2^63 a 2^63-1.</p><p>Formato JSON: Número</p></td>
        <td>&lt;valor entero&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Número decimal.</p><p>Representa un valor flotante:</p>
        <p>- valor finito positivo más alto de tipo doble, (2-2^-52)x2^1023</p>
        <p> - valor normal positivo mínimo del tipo doble, 2-1022</p>
        <p> - valor mínimo positivo distinto de cero de tipo doble, 2 p-1074</p><p>Formato JSON: Número</p><p>Formato de serialización: usando '.' como separador decimal.</p></td>
        <td>&lt;valor entero&gt;.&lt;valor entero&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>booleano</td>
        <td><p>Valor booleano escrito en minúsculas: true o false</p><p>Formato JSON:Booleano</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Representa una fecha y hora sin zona horaria, vista como año-mes-día-hora-minuto-segundo-milisegundo.</p><p>No almacena ni representa un huso horario.</p><p>En cambio, es una descripción de la fecha, como se usa para los cumpleaños, combinada con la hora local como se ve en un reloj de pared.</p><p>No puede representar un instante en la línea de tiempo sin información adicional como un desplazamiento o una zona horaria.</p><p>Formato de serialización: Formato de fecha y hora de desplazamiento ampliado ISO-8601.</p><p>Utiliza DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME para deserializar y serializar el valor.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Más información</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly en formato ISO-8601&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Constante de fecha y hora que también tiene en cuenta la zona horaria.</p><p>Representa una fecha y hora con un desplazamiento de UTC. Se puede ver como un instante en el tiempo con la información adicional del desplazamiento. </p><p>Es una manera de representar un "momento" específico en un determinado lugar del mundo.</p><p>Formato JSON: Cadena.</p><p> Debe encapsularse en una función toDateTime.</p><p>
        Formato de serialización: Formato de fecha y hora de desplazamiento ampliado ISO-8601.</p><p> Utiliza DateTimeForsubject.ISO_OFFSET_DATE_TIME para deserializar y serializar el valor.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Más información</a>. 
        <p>También puede pasar un entero que pase un valor epoch.</p> <a href="https://www.epochconverter.com/">Más información</a>.</p>
        <p>La zona horaria se puede especificar mediante un desplazamiento o un código de zona horaria (ejemplo: Europa/París, Z (es decir, UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime en formato ISO-8601&gt;")</p>
        <p>toDateTime(&lt;valor entero de una epoch en milisegundos&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>Representa una cantidad de tiempo basada en el tiempo, como "34,5 segundos".</p><p> Modela una cantidad o cantidad de tiempo en milisegundos.</p><p>Las unidades temporales admitidas son: milisegundos, segundos, minutos, horas, días en los que un día equivale a 24 horas.</p><p> No se admiten años y meses porque no son una cantidad de tiempo fija.</p><p>Formato JSON: Cadena. Debe encapsularse en una función toDuration.</p><p>Formato de serialización: Para deserializar un ID de zona horaria, utiliza la función java java.time.</p><p>Duration.parse: los formatos aceptados se basan en el formato de duración ISO-8601 PnDTnHnMn.nS con días considerados exactamente como 24 horas.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Más información</a>.</td>
        <td><p>toDuration("&lt;duración en formato ISO-8601&gt;")</p><p>toDuration(&lt;duración en milisegundos&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 segundos</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— analiza como "20,345 segundos"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — se analiza como "15 minutos"</pre></p>
        <p><pre>(donde un minuto es de 60 segundos)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— se analiza como "10 horas"</pre></p>
        <p><pre>(donde una hora es de 3600 segundos)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— analiza como "2 días"</pre></p>
        <p><pre>(donde un día es </pre></p>
        <p><pre>24 horas u 86400 segundos)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— analiza como</pre></p>
        <p><pre>"2 días, 3 horas y 4 minutos"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— analiza como</pre></p>
        <p><pre>"-6 horas y +3 minutos"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— analiza como</pre></p>
        <p><pre>"-6 horas y -3 minutos"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— analiza como</pre></p>
        <p><pre>"+6 horas y -3 minutos"</pre></p></td>
    </tr>
    <tr>
        <td>lista</td>
        <td>Lista de expresiones separadas por comas que utilizan corchetes como delimitadores. No se admite el polimorfismo, por lo que todas las expresiones incluidas en la lista deben tener el mismo tipo.</td>
        <td>[&lt;expresión&gt;, &lt;expresión&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
