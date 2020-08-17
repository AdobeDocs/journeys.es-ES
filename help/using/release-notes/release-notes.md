---
title: Notas de la versión
description: Más información sobre las notas de la versión
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
source-git-commit: 8641b577e91492c86e6fc8e201acd6a208e5e38b
workflow-type: tm+mt
source-wordcount: '1107'
ht-degree: 84%

---


# Notas de la versión {#release-notes}

Esta página lista todas las nuevas funciones y mejoras de Journey Orchestration.
También puede consultar las [Actualizaciones de documentación](../release-notes/documentation-updates.md).

## Versión del segundo trimestre de 2020 {#q2-release---june-2020}

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
<li><p>Una nueva actividad permite escuchar las entradas y salidas de segmentos de Adobe Experience Platform para hacer que las personas entren o avancen en un viaje. <a href="../building-journeys/segment-qualification-events.md">Más información</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Adobe Experience Platform segments can now be created and edited without leaving the Journey Orchestration interface, thanks to a new <strong>Segments</strong> tab.<a href="../segment/about-segments.md">Más información</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>En el editor de expresiones sencillo, los segmentos de Adobe Experience Platform ahora se muestran directamente en el árbol de navegación para permitir una configuración sencilla de condiciones como "¿Pertenece esta persona al segmento A?".<a href="../segment/using-a-segment.md">Más información</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Ahora el Journey Orchestration pasa automáticamente a Adobe Experience Platform los pasos ejecutados en los viajes. Esto incluye los posibles errores encontrados. Esta información se puede utilizar para lograr sistemas de informes y solucionar problemas mediante la ejecución de consultas en los eventos del paso del recorrido para un recorrido determinado o para todos ellos. <a href="../building-journeys/sharing-overview.md">Más información</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>Ahora, el Journey Orchestration puede conectarse a los entornos limitados Adobe Experience Platform de producción y sin producción. Tenga en cuenta que los entornos limitados son una función beta. <a href="../about/access-management.md#sandboxes">Más información</a></p>
</li>
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

## Versión del primer trimestre de 2020 {#q1-release---march-2020}

**Novedades**

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
<li>The <strong>Profile Timezone</strong> checkbox allows you to use the Adobe Experience Platform Profile timezone of the person entering the journey, if available. Si no es así, se utiliza la zona horaria definida en la lista desplegable. Esta función no es compatible con los recorridos que utilizan eventos que no tienen área de nombres.</li>
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

* In addition to US, Journey Orchestration is now available in **EMEA**. La aplicación y la documentación están disponibles en francés y alemán.

* Experience League está ahora integrada en el producto. Esto simplifica el acceso al contenido relacionado y le ayuda a sacar el máximo provecho de Experience Cloud. El acceso directo a la documentación de Journey Orchestration está disponible en la parte inferior de la pestaña Ayuda. Además, haga clic en Ayuda > Comentarios para informar sobre problemas o compartir sus ideas con Adobe.

* El método abreviado de teclado **C** , que le permite crear un nuevo elemento, ya está disponible en todas las pantallas de lista: recorridos, fuentes de datos, acciones y eventos. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)

* Ahora puede **eliminar** los recorridos detenidos. Los informes asociados a estos recorridos eliminados no estarán disponibles.

* When browsing through **Adobe Experience Platform fields** (XDM format), you will now see the display name in addition to the field name. Esta información se recupera de la definición de esquema del modelo de datos de Experience. Cuando está disponible, aparece el nombre para mostrar alternativo. Esta descripción sencilla, especialmente útil en el caso de los campos eVar, permite identificar los campos con mayor facilidad. [Más información](../about/user-interface.md#friendly-names-display)

## Versión de GA: diciembre de 2019 {#ga-release---december-2019}

Journey Orchestration es ahora GA.

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

Journey Orchestration permite la orquestación en tiempo real basada en datos contextuales de eventos, información de Adobe Experience Platform o datos de servicios API de terceros. La aplicación determina en los flujos de varios pasos llamados recorridos las siguientes mejores acciones específicas del consumidor, en función de su perfil y comportamiento. Esto incluye tanto el momento óptimo como el tipo de acción, como enviar al consumidor una notificación push a través de las funciones de mensajería transaccional de Adobe Campaign Standard (requiere Adobe Campaign Standard) o la notificación de un sistema de terceros. Estas decisiones se toman en base a reglas y puntuaciones de Sensei.

[](../action/working-with-adobe-campaign.md)Obtenga más información sobre Journey Orchestration.

Recursos adicionales:

* [Tutoriales](https://docs.adobe.com/content/help/es-ES/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Comunidad](https://www.adobe.com/go/journeyorchestrationcommunity)
