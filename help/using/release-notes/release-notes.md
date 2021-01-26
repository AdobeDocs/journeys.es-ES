---
product: adobe campaign
solution: Journey Orchestration
title: Notas de la versión
description: Más información sobre las notas de la versión
translation-type: tm+mt
source-git-commit: c7eb29c873f91ed1debe4e8c786a96a1f6b71b71
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 73%

---


# Notas de la versión {#release-notes}

Esta página lista todas las nuevas funciones y mejoras de Journey Orchestration.
También puede consultar las [Actualizaciones de documentación](../release-notes/documentation-updates.md) más recientes.

## Versión de enero de 2021 {#january-release}

Al seleccionar un esquema en la configuración de evento, solo se seleccionan los campos obligatorios para que el Journey Orchestration reciba el evento correctamente. [Puede obtener más información](../event/defining-the-payload-fields.md)

Los atributos de las propiedades de recorrido ahora están disponibles en el editor de expresiones sencillo. [Puede obtener más información](../expression/journey-properties.md)

Se han agregado dos atributos de propiedades de recorrido nuevos (sandboxName y OrganizationId). [Puede obtener más información](../expression/journey-properties.md)

Para alinearse con los SLA de Adobe Campaign Standard, ahora se define automáticamente una regla de límite de 13 llamadas por segundo para acciones de Adobe Campaign Standard en cuanto se configura la integración de Adobe Campaign Standard. [Puede obtener más información](../action/working-with-adobe-campaign.md)

La duración del tiempo de espera de evento ahora se especifica con mayor claridad en la ruta de tiempo de espera. [Puede obtener más información](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

Las funciones [getListItem](../functions/functiongetlistitem.md) y [split](../functions/functionsplit.md) se han agregado a la lista de funciones disponibles en el editor de expresiones avanzado. Esto oferta más posibilidades en los casos de uso de cálculos de cadenas.

## Versión de noviembre de 2020 {#november-release}

<table>
<thead>
<tr>
<th><strong>Saltar de un recorrido a otro</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Una nueva actividad de acción permite insertar individuos de un recorrido a otro. La actividad <strong>Jump</strong> le permite:
</p>
<ul>
<li>simplificar el diseño de recorridos muy complejos dividiéndolos en varios </li>
<li>generar recorridos basados en patrones de recorrido comunes y reutilizables</li>
</ul>
<p>Para obtener más información, consulte la <a href="../building-journeys/jump.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html">videotutorial</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Uso de las propiedades de recorrido en el editor de expresiones</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En el editor de expresiones avanzado, hemos agregado una nueva categoría en la lista de campos y funciones. Es la información recuperada por el sistema de recorridos activos, como el ID de recorrido o los errores específicos encontrados. Esto le dará más posibilidades al construir sus recorridos. Por ejemplo, podrá avisar a sistemas de terceros en caso de que se produzcan errores en una condición o una acción.
</p>
<p>Para obtener más información, consulte la <a href="../expression/journey-properties.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos basados en reglas (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ahora hay disponible un nuevo método para configurar sus eventos más fácilmente, sin usar un eventID: los eventos basados en reglas evalúan si el evento debe activarse según una condición. Puede seguir utilizando el método existente, ahora denominado "generado por el sistema". Esta función, que se ha probado entre un conjunto limitado de clientes a través del programa Alpha, ahora está disponible en versión beta para todos los clientes.
</p>
<p>Para obtener más información, consulte la <a href="../event/about-events.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Otras mejoras

Se han agregado limitaciones al crear nuevas versiones de un recorrido. Estas limitaciones evitan cambios demasiado drásticos en el recorrido para mantener cierta coherencia entre las versiones. [Puede obtener más información](../about/limitations.md#journey-versions-limitations)

La actividad **Calificación del segmento** ya no se puede usar en un recorrido que incluya actividades de mensajes de Campaign Standard. Esta restricción protege la integridad de las instancias de Adobe Campaign Standard. De hecho, el uso de Calificación de segmentos puede llevar a picos diarios de envío de mensajes que sobrecargarían la mensajería transaccional de Campaign Standards. [Puede obtener más información](../about/limitations.md#segment-qualification)

## Versión de octubre de 2020 {#october-release}

<table>
<thead>
<tr>
<th><strong>Tiempo de espera de evento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ahora puede configurar un tiempo de espera para un evento para que un recorrido escuche un evento solo durante un tiempo determinado. Ya no necesita agregar una actividad de espera en paralelo a la ruta de evento para lograrlo.
</p>
<p>Para obtener más información, consulte la <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Otras mejoras

* Al publicar una nueva versión de un recorrido, la versión anterior finaliza automáticamente y cambia al estado Cerrado. [Puede obtener más información](../building-journeys/journey-versions.md)

## Versión de septiembre de 2020 {#september-release}

### Actualizaciones de GA{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Mejoras en la actividad de condiciones</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Al agregar condiciones al recorrido, ahora puede definir una etiqueta. Si utiliza varias condiciones en un recorrido, esto le permite identificarlas con mayor facilidad.
</p>
<p>Para obtener más información, consulte la <a href="../building-journeys/condition-activity.md#about_condition">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Actualizaciones Alpha{#september-alpha-update}

Para descubrir el ámbito de Alpha, consulte esta [sección](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Leer las mejoras en la actividad de segmentos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en la actividad <strong>Leer segmento</strong>:
</p>
<ul>
<li><p>Los recorridos basados en segmentos ahora muestran, encima del lienzo, un recordatorio del tipo de programación del recorrido. Puede hacer clic en este recordatorio para acceder al menú de configuración de programación.</p>
</li>
<li><p>Se ha mejorado la granularidad de los registros de modo de prueba para mostrar el estado de progreso de exportación de segmentos.</p>
</li>
</ul>
<p>Para obtener más información sobre la actividad <strong>Leer segmento</strong>, consulte la <a href="../alpha/alpha-segment-trigger.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

## Versión de agosto de 2020 {#august-release}

### Actualizaciones de GA{#august-ga-update}

La carga de los eventos de calificación de segmentos ahora contiene la siguiente información de contexto que puede utilizar en condiciones y acciones: el comportamiento (entrada y salida), la marca de tiempo de la cualificación y la ID de segmento. [Más información](../building-journeys/segment-qualification-events.md)

### Actualizaciones Alpha{#august-alpha-update}

Para descubrir el ámbito de Alpha, consulte esta [sección](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Actividad del activador de segmentos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en la actividad del activador de segmentos:
</p>
<ul>
<li><p>El nombre de la actividad se cambió a "Leer segmento". </p>
</li>
<li><p>La configuración del Planificador de recorrido se ha eliminado de las propiedades de la actividad. Ahora es accesible directamente desde las propiedades del recorrido, en una sección dedicada que se muestra si se ha colocado una actividad Leer segmento en el lienzo. </p>
</li>
<li><p>Ahora puede probar el recorrido en un perfil unitario y rastrear su progreso de recorrido utilizando el flujo visual.</p>
</li>
</ul>
<p>Para obtener más información, consulte la <a href="../alpha/alpha-segment-trigger.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos basados en reglas</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en los eventos basados en reglas:
</p>
<ul>
<li><p>Ahora puede aprovechar todos los datos de evento de comportamiento de Adobe Analytics que ya está capturando y transmitiendo a la plataforma para activar los recorridos y automatizar las experiencias para sus clientes. <a href="../event/about-analytics.md">Más información</a></p>
</li>
<li><p>Al activar un evento basado en reglas en el modo de prueba, ahora puede realizar la vista directa de la condición de ID de evento. Además, se añade la información sobre herramientas junto a cada campo que forma parte de la evaluación de reglas. <a href="../building-journeys/testing-the-journey.md#test-rule-based">Más información</a></p>
</li>
<li><p>La pantalla de definición de evento basado en reglas se reorganizó para mejorar la experiencia. <a href="../event/about-creating.md">Más información</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Versión Alpha: julio de 2020 {#alpha-release---july-2020}

El programa Alpha ofrece características que actualmente están siendo probadas entre un grupo limitado de clientes. Esto nos permite mejorar nuestro producto en base a los comentarios recibidos. Estas características no están disponibles para todos los clientes Journey Orchestration.

Estas características se describen en una [sección](../alpha/alpha-overview.md) dedicada.

<table>
<thead>
<tr>
<th><strong>Interfaz de usuario mejorada</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se ha mejorado la navegación dentro de los menús del Journey Orchestration para proporcionar una interfaz coherente con Adobe Experience Platform:
</p>
<ul>
<li><p>Los menús se mueven desde la parte superior hacia la izquierda de la interfaz. </p>
</li>
<li><p>Agrupación de funcionalidades administrativas en un solo panel.</p>
</li>
</ul>
<p>Para obtener más información, consulte la <a href="../alpha/alpha-interface.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Actividad del activador de segmentos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La Actividad del activador de segmentos le permite hacer que todas las personas que pertenecen a un segmento de Adobe Experience Platform participen en un recorrido. La entrada en un recorrido puede realizarse una vez o de forma regular. <a href="../alpha/alpha-segment-trigger.md">Más información</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos basados en reglas</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Hemos simplificado la forma de configurar el Evento de Experience. Presentamos un nuevo método que no requiere el uso de un ID de evento. Al configurar el evento en Journey Orchestration, ahora puede definir un evento basado en reglas. <a href="../event/about-events.md">Más información</a>
</p>
</td>
</tr>
</tbody>
</table>


## Versión del segundo trimestre, junio de 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Mejoras en la integración de Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en la integración de Adobe Experience Platform:</p>
<ul>
<li><p>Una nueva actividad permite escuchar las entradas y salidas de segmentos de Adobe Experience Platform para hacer que las personas entren o avancen en un recorrido. <a href="../building-journeys/segment-qualification-events.md">Más información</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Los segmentos de Adobe Experience Platform ahora se pueden crear y editar sin salir de la interfaz de Journey Orchestration, gracias a la nueva pestaña <strong>Segmentos</strong> . <a href="../segment/about-segments.md">Puede obtener más información</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>En el editor de expresiones simple, los segmentos de Adobe Experience Platform ahora se muestran directamente en el árbol de navegación para permitir una configuración sencilla de condiciones como "¿Pertenece esta persona al segmento A?". <a href="../segment/using-a-segment.md">Más información</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Ahora Journey Orchestration pasa automáticamente a Adobe Experience Platform los pasos que se ejecutan en los recorridos. Esto incluye los posibles errores encontrados. Esta información se puede utilizar para lograr sistemas de informes y solucionar problemas mediante la ejecución de consultas en los eventos del paso del recorrido para un recorrido determinado o para todos ellos. <a href="../building-journeys/sharing-overview.md">Más información</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Ahora, Journey Orchestration puede conectarse a los entornos limitados de la Adobe Experience Platform de producción y sin producción. Tenga en cuenta que los entornos limitados son una función beta. <a href="../about/access-management.md#sandboxes">Más información</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mejoras del modo de prueba y diseñador de recorridos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en el diseñador de recorridos y en el modo de prueba:</p>
<ul>
<li><p>Ahora puede copiar actividades de pegado de un recorrido a otro seleccionando una o N actividades de recorrido. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Más información</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Después de activar un evento para hacer que un perfil de prueba entre en un recorrido, ahora puede ver su progreso a lo largo de este gracias a un flujo visual de color. En caso de error en el recorrido, también se muestran los detalles de los errores. <a href="../building-journeys/testing-the-journey.md#firing_events">Más información</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>El estado del recorrido <strong>terminado</strong> se ha cambiado a <strong>Cerrado (sin entrada)</strong> para reflejar mejor lo que significa este estado.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Otras mejoras**

Para evitar el envío de demasiadas llamadas API a sistemas de terceros, estamos introduciendo una nueva API pública para configurar reglas de &quot;restricción&quot;. Las reglas de restricción permiten la definición de un número máximo de llamadas a un extremo de API por milisegundos. [Más información](../api/capping.md)

Control de acceso ahora permite una mayor granularidad en la administración de acceso de los usuarios. Disponibilidad desde: 30 de junio de 2020. [Más información](../about/access-management.md#create-product-profile)

Journey Orchestration ahora está disponible en APAC (centro de datos australiano). Disponibilidad desde: 30 de junio de 2020

La interfaz de Journey Orchestration está disponible en japonés.

## Versión del primer trimestre, marzo de 2020 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>Mejoras del modo de prueba</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Se han realizado las siguientes mejoras en el modo de prueba:</p>
<ul>
<li>Cuando un recorrido utiliza varios eventos, ahora puede activarlos individualmente desde una lista desplegable, en la pantalla del modo de prueba <strong>Evento de configuración</strong>. <a href="../building-journeys/testing-the-journey.md#firing_events">Más información</a></p></li>
<li><p>Cuando se utilizan una o varias actividades de <strong>espera</strong> en un recorrido, ahora puede definir el tiempo que cada una de estas actividades durará en el modo de prueba. El valor del tiempo predeterminado es de 10 segundos. Puede cambiar esto usando el parámetro <strong>Tiempo de espera en prueba</strong>, en la esquina inferior izquierda. <a href="../building-journeys/testing-the-journey.md">Más información</a></p><img src="../assets/rn-test.png"/>
</li>
<li>En los <strong>registros de prueba</strong>, en caso de error al llamar a un sistema de terceros (fuente de datos o acción), ahora se muestran el código de error y la respuesta de error. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Más información</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Administración centralizada de huso horario</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La administración de zonas horarias ahora está centralizada en el panel de propiedades del recorrido. Se han añadido dos parámetros en las propiedades del recorrido:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>La lista desplegable <strong>Zona horaria</strong> permite seleccionar una zona horaria específica. De forma predeterminada, se utiliza la zona horaria del explorador. </li>
<li>La casilla <strong>Zona horaria del perfil</strong> le permite utilizar la zona horaria del perfil de Adobe Experience Platform de la persona que entra en el recorrido si está disponible. Si no es así, se utiliza la zona horaria definida en la lista desplegable. Esta función no es compatible con los recorridos que utilizan eventos que no tienen área de nombres.</li>
</ul>
<p>Para obtener más información, consulte las secciones <a href="../building-journeys/changing-properties.md#timezone">Cambio de las propiedades</a> y <a href="../building-journeys/timezone-management.md">Administración de zonas horarias</a> .</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mejoras en el diseñador de recorridos</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Se ha mejorado la <strong>paleta</strong> de recorrido, situada en la parte izquierda del diseñador de recorridos:</p>
<ul>
<li>Un nuevo icono, junto a la barra de <strong>búsqueda</strong>, permite ocultar o mostrar elementos no disponibles en la paleta como eventos que utilizan un área de nombres diferente a la utilizada en el recorrido. De forma predeterminada, los elementos no disponibles están ocultos.</li>
<li>Al utilizar el campo <strong>Buscar</strong>, ahora se muestra el número de resultados de cada categoría de actividad de lienzo.</li>
<li>Se ha mejorado la navegación entre las distintas categorías de actividad.</li>
</ul>
<p>En el diseñador de recorridos, ahora puede comprobar que está accediendo a la última versión del recorrido. Esta información se muestra junto al número de versión.</p>
<p>En el <strong>lienzo</strong> del recorrido, cuando se desconectan dos actividades, ahora se muestra un mensaje de advertencia.</p>
<img src="../assets/rn-canvas.png"/>
<p>Para obtener más información, consulte la <a href="../building-journeys/using-the-journey-designer.md">documentación detallada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Ayuda contextual</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ahora hay disponible una ayuda contextual en las distintas pantallas de lista de Journey Orchestration (recorridos, eventos, acciones y fuentes de datos). Esto le permite realizar una vista rápida de la funcionalidad actual y acceder a los artículos y vídeos relacionados.</p>
<p>Para mostrar la ayuda contextual, haga clic en el icono <img src="../assets/icon-context.png"/>, en la esquina superior derecha de la pantalla. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Otras mejoras**

* Además de EE. UU., Journey Orchestration ya está disponible en **EMEA**. La aplicación y la documentación están disponibles en francés y alemán.

* Experience League está ahora integrada en el producto. Esto simplifica el acceso al contenido relacionado y le ayuda a sacar el máximo provecho de Experience Cloud. El acceso directo a la documentación de Journey Orchestration está disponible en la parte inferior de la pestaña Ayuda. Además, haga clic en Ayuda > Comentarios para informar sobre problemas o compartir sus ideas con Adobe.

* El método abreviado de teclado **C** , que le permite crear un nuevo elemento, ya está disponible en todas las pantallas de lista: recorridos, fuentes de datos, acciones y eventos. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)

* Ahora puede **eliminar** los recorridos detenidos. Los informes asociados a estos recorridos eliminados no estarán disponibles.

* Al navegar por los **campos de Adobe Experience Platform** (en formato XDM), ahora verá el nombre en pantalla además del nombre de campo. Esta información se recupera de la definición de esquema del modelo de datos de Experience. Cuando está disponible, aparece el nombre para mostrar alternativo. Esta descripción sencilla, especialmente útil en el caso de los campos eVar, permite identificar los campos con mayor facilidad. [Más información](../about/user-interface.md#friendly-names-display)

## Versión de GA: diciembre de 2019 {#ga-release---december-2019}

Journey Orchestration es ahora GA.

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

Journey Orchestration permite la orquestación en tiempo real basada en datos contextuales de eventos, información de Adobe Experience Platform o datos de servicios API de terceros. La aplicación determina en los flujos de varios pasos llamados recorridos las siguientes mejores acciones específicas del consumidor, en función de su perfil y comportamiento. Esto incluye tanto el momento óptimo como el tipo de acción, como enviar al consumidor una notificación push a través de las funciones de mensajería transaccional de Adobe Campaign Standard (requiere Adobe Campaign Standard) o la notificación de un sistema de terceros. Estas decisiones se toman en base a reglas y puntuaciones de Sensei.

[](../action/working-with-adobe-campaign.md)Obtenga más información sobre Journey Orchestration.

Recursos adicionales:

* [Tutoriales](https://docs.adobe.com/content/help/es-ES/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Comunidad](https://www.adobe.com/go/journeyorchestrationcommunity)
