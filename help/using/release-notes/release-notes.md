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
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d

---


# Notas de la versión {#release-notes}

Esta página lista todas las nuevas funciones y mejoras para la orquestación de viajes.
También puede consultar las Actualizaciones [de](../release-notes/documentation-updates.md)documentación.

## Versión del primer trimestre de 2020 {#q1-release---march-2020}

**Novedades?**

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
<li>Cuando un viaje utiliza varios eventos, ahora puede activarlos individualmente desde una lista desplegable, en la pantalla de configuración <strong>de</strong> Evento del modo de prueba. <a href="../building-journeys/testing-the-journey.md#firing_events">Más información</a></p></li>
<li><p>Cuando se utilizan una o varias actividades de <strong>espera</strong> en un viaje, ahora puede definir el tiempo que cada una de estas actividades durará en el modo de prueba. El tiempo predeterminado es de 10 segundos. Puede cambiar esto usando el parámetro <strong>Tiempo de espera en el parámetro de prueba</strong> , en la esquina inferior izquierda. <a href="../building-journeys/testing-the-journey.md">Más información</a></p><img src="../assets/rn-test.png"/>
</li>
<li>En los registros <strong>de</strong>prueba, en caso de error al llamar a un sistema de terceros (fuente de datos o acción), ahora se muestran el código de error y la respuesta de error. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Más información</a>
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
<p>La administración de zonas horarias ahora está centralizada en el panel de propiedades del viaje. Se han añadido dos parámetros en las propiedades del viaje:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>La lista desplegable <strong>Zona horaria</strong> permite seleccionar una zona horaria específica. De forma predeterminada, se utiliza la zona horaria del explorador. </li>
<li>La casilla de verificación Zona horaria <strong>de</strong> Perfil le permite utilizar la zona horaria de Perfil de la plataforma de experiencia de la persona que entra en el viaje, si está disponible. Si no es así, se utiliza la zona horaria definida en la lista desplegable. Esta función no es compatible con los viajes que utilizan eventos que no tienen Área de nombres.</li>
</ul>
<p>Para obtener más información, consulte las secciones <a href="../building-journeys/changing-properties.md#timezone">Cambio de propiedades</a> y Administración de <a href="../building-journeys/timezone-management.md">zonas horarias</a> .</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Mejoras en el diseñador de viajes</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Se ha mejorado la <strong>paleta</strong>de viaje, situada en la parte izquierda del diseñador del viaje:</p>
<ul>
<li>Un nuevo icono, junto a la barra de <strong>búsqueda</strong> , permite ocultar o mostrar elementos no disponibles en la paleta, por ejemplo los eventos que utilizan una Área de nombres diferente a la utilizada en el viaje. De forma predeterminada, los elementos no disponibles están ocultos.</li>
<li>Al utilizar el campo <strong>Buscar</strong> , ahora se muestra el número de resultados de cada categoría de actividad de lienzo.</li>
<li>Se ha mejorado la navegación entre las distintas categorías de actividad.</li>
</ul>
<p>En el diseñador de viajes, ahora puede comprobar que está accediendo a la última versión del viaje. Esta información se muestra junto al número de versión.</p>
<p>En el <strong>lienzo</strong>del viaje, cuando se desconectan dos actividades, ahora se muestra un mensaje de advertencia.</p>
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
<p>Ahora hay disponible una ayuda contextual en las distintas pantallas de lista de orquestación de viajes (viajes, eventos, acciones y fuentes de datos). Esto le permite realizar una vista rápida de la funcionalidad actual y acceder a los artículos y vídeos relacionados.</p>
<p>Para mostrar la ayuda contextual, haga clic en el <img src="../assets/icon-context.png"/> icono en la esquina superior derecha de la pantalla. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Otras mejoras**

* Además de EE.UU., la orquestación de travesías ya está disponible en **EMEA**. La aplicación y la documentación están disponibles en francés y alemán.

* Experience League está ahora integrada en el producto. Esto simplifica el acceso al contenido relacionado y le ayuda a sacar el máximo provecho de Experience Cloud. El acceso directo a la documentación de orquestación de viajes está disponible en la parte inferior de la ficha Ayuda. Además, haga clic en Ayuda > Comentarios para informar sobre problemas o compartir sus ideas con Adobe.

* El método abreviado de teclado **C** , que le permite crear un nuevo elemento, ya está disponible en todas las pantallas de lista: viajes, fuentes de datos, acciones y eventos. [Más información](../about/user-interface.md#section_ksq_zr1_ffb)

* Ahora puede **eliminar** los viajes detenidos. Los informes asociados a estos viajes eliminados no estarán disponibles.

* Al navegar por los campos **Plataforma** de datos (formato XDM), ahora verá el nombre para mostrar además del nombre del campo. Esta información se recupera de la definición de esquema del modelo de datos de experiencia. Cuando está disponible, aparece el nombre para mostrar alternativo. Esta descripción sencilla, especialmente útil en el caso de los campos eVar, permite identificar los campos con mayor facilidad. [Más información](../about/user-interface.md#friendly-names-display)

## Versión de GA - Diciembre de 2019 {#ga-release---december-2019}

La orquestación de viajes es ahora GA.

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

La orquestación de viajes permite la orquestación en tiempo real basada en datos contextuales de eventos, información de la plataforma Adobe Experience o datos de servicios API de terceros. La aplicación determina en los flujos de varios pasos llamados viajes las siguientes mejores acciones específicas del consumidor, en función de su perfil y comportamiento. Esto incluye tanto el momento óptimo como el tipo de acción, como enviar al consumidor una notificación push a través de las capacidades de mensajería transaccional de Adobe Campaign Standard (requiere Adobe Campaign Standard) o la notificación de un sistema de terceros. Estas decisiones se toman en base a reglas y puntuaciones Sensei.

[](../action/working-with-adobe-campaign.md)Obtenga más información sobre Journey Orchestration.

Recursos adicionales:

* [Tutoriales](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Comunidad](https://www.adobe.com/go/journeyorchestrationcommunity)
