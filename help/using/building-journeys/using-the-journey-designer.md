---
title: Uso del diseñador de recorridos
description: Obtenga más información sobre el uso del diseñador de viajes
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
source-git-commit: 27cd94ec9da9e89d62ec8e4f471dab43d2e9e657
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 5%

---


# Uso del diseñador de recorridos {#concept_m1g_5qt_52b}

El menú Inicio del viaje le permite vista de la **lista de los viajes**. Cree un nuevo viaje o haga clic en uno existente para abrir la interfaz **del diseñador del** viaje. El diseñador se compone de las siguientes zonas: la paleta, el lienzo y el panel de configuración de la actividad.

## La lista del viaje {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. Puede duplicar, detener o eliminar recorridos. Según el recorrido, es posible que algunas acciones no estén disponibles. Por ejemplo, no se puede eliminar ni reiniciar un recorrido cerrado. Puede crear una nueva versión a partir de ella, duplicado o deteniéndola. También puede utilizar la barra de búsqueda para buscar un recorrido.

Se puede acceder a **[!UICONTROL Filters]** haciendo clic en el icono de filtro en la parte superior izquierda de la lista. El menú filtros le permite filtrar los viajes mostrados según diferentes criterios (estado, los que ha creado, los modificados en los últimos 30 días, versiones más recientes, etc.). También puede elegir mostrar únicamente los viajes que utilizan un evento, un grupo de campos o una acción concretos. Se pueden configurar las columnas que se muestran en la lista. Todos los filtros y columnas se guardan por usuario.

![](../assets/journey74.png)

Todas las versiones de sus viajes aparecen en la lista con el número de versión. Consulte [](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Para abrir el lienzo de un viaje en otra ficha del navegador, mantenga pulsada la tecla **Control** o **Comando** y haga clic en el viaje.

## La paleta {#palette}

La **paleta** se encuentra en el lado izquierdo de la pantalla. Todas las actividades disponibles se ordenan en varias categorías: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** y **[!UICONTROL Actions]**. Puede expandir o contraer las diferentes categorías haciendo clic en su nombre. Para utilizar una actividad en el viaje, arrástrela y suéltela desde la paleta en el lienzo. También puede hacer clic con el botón doble en una actividad de la paleta para agregarla al lienzo, en el siguiente paso disponible. Debe configurar cada actividad añadida desde la paleta antes de publicar el viaje. Si suelta una actividad en el lienzo y no termina su configuración, permanecerá en el lienzo, pero una advertencia roja indicará que la configuración no ha finalizado para esta actividad.

>[!NOTE]
>
>Tenga en cuenta que existen reglas al configurar un viaje. Se descartará la configuración no permitida. Por ejemplo, no puede colocar acciones en paralelo, vincular una actividad a un paso anterior para crear un bucle, inicio de un viaje con algo distinto a un evento, etc.

![](../assets/journey38.png)

The **[!UICONTROL Show disabled items]** icon in the top left corner allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. De forma predeterminada, los elementos no disponibles están ocultos. Si elige mostrarlos, aparecerán atenuados.

Al utilizar el **[!UICONTROL Search]** campo, se muestra el número de resultados para cada categoría de actividad de lienzo.

![](../assets/palette-filter.png)

## El lienzo {#canvas}

El **lienzo** es la zona central del diseñador de viajes. Es en esta zona donde puede soltar sus actividades y configurarlas. Haga clic en una actividad del lienzo para configurarla. Esto abre el panel de configuración de actividad en el lado derecho. Puede acercar y alejar con los botones &quot;+&quot; y &quot;-&quot; de la parte superior derecha. En el lienzo, todas las actividades permiten agregar un paso siguiente después de ellas, excepto **[!UICONTROL End]** actividades (ver [](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Panel de configuración de actividad {#configuration_pane}

El panel **de configuración de la** actividad aparece al hacer clic en una actividad de la paleta. Rellene los campos obligatorios. Haga clic en el **[!UICONTROL Delete]** icono para eliminar la actividad. Haga clic en **[!UICONTROL Cancel]** para cancelar las modificaciones o **[!UICONTROL Ok]** confirmar. Para eliminar actividades, también puede seleccionar una actividad (o varias) y pulsar la tecla de retroceso. Al pulsar la tecla de escape se cerrará el panel de configuración de la actividad.

En el lienzo, las actividades de acción y evento se representan con un icono con el nombre del evento o la acción que se muestra debajo. En el panel de configuración de actividad, puede utilizar el **[!UICONTROL Label]** campo para agregar un sufijo al nombre de la actividad. Estas etiquetas le ayudarán a contextualizar el uso de eventos y acciones, especialmente cuando utiliza el mismo evento o acción varias veces en el viaje. También podrá ver las etiquetas agregadas en el [!DNL Journey Orchestration] sistema de informes. También puede definir etiquetas para las actividades de condiciones.

![](../assets/journey59bis.png)

## Acciones de la barra superior {#top_actions}

Según el estado del viaje, puede realizar diferentes acciones en el viaje con los botones disponibles en la esquina superior derecha: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Estos botones aparecen cuando no hay ninguna actividad seleccionada. Algunos botones aparecerán contextualmente. El botón de registro del modo de prueba aparece cuando se activa el modo de prueba (consulte [](../building-journeys/testing-the-journey.md)). El botón de sistema de informes aparece cuando el viaje está activo, detenido o cerrado.

![](../assets/journey41.png)

## Uso de rutas en el lienzo {#paths}

Varias actividades (**[!UICONTROL Condition]**, **[!UICONTROL Action]** actividades) permiten definir una acción de reserva en caso de error o de tiempo de espera. En el panel de configuración de actividad, marque la casilla: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se agrega otra ruta después de la actividad. La duración del tiempo de espera se define en las propiedades del viaje (consulte [](../building-journeys/changing-properties.md) por un usuario administrador. Por ejemplo, si un correo electrónico tarda demasiado en enviarse o se produce un error, puede decidir enviar un mensaje de texto.

![](../assets/journey42.png)

Varias actividades (evento, acción, espera) permiten agregar varias rutas después de ellas. Para ello, coloque el cursor en la actividad y haga clic en el símbolo &quot;+&quot;. Solo se pueden establecer actividades de evento y espera en paralelo. Si se configuran varios eventos en paralelo, la ruta elegida será la del primer evento que se produzca.

Al escuchar un evento, le recomendamos que no espere indefinidamente al evento. No es obligatorio, sino una práctica recomendada. Si desea escuchar uno o varios eventos solo durante un tiempo determinado, colocará uno o varios eventos y una actividad de espera en paralelo. Consulte [](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Para eliminar la ruta, coloque el cursor sobre ella y haga clic en el **[!UICONTROL Delete arrow]** icono .

![](../assets/journey42ter.png)

En el lienzo, cuando se desconectan dos actividades, se muestra una advertencia. Coloque el cursor en el icono de advertencia para mostrar el mensaje de error. Para solucionar el problema, simplemente mueva la actividad desconectada y conéctela a la actividad anterior.

![](../assets/canvas-disconnected.png)

## Copia y pegado de actividades {#copy-paste}

Puede copiar una o varias actividades de un viaje y pegarlas en el mismo viaje o en otro. Esto le permite ahorrar tiempo si desea reutilizar numerosas actividades que ya se han configurado en un viaje anterior.

**Notas importantes**

* Puede copiar/pegar en diferentes fichas y navegadores. Solo puede copiar/pegar actividades en la misma instancia.
* No puede copiar/pegar un evento si el viaje de destino tiene un evento que utilice una Área de nombres diferente.
* Las actividades pegadas pueden hacer referencia a datos que no existen en el viaje de destino, por ejemplo, si copia o pega en distintos entornos limitados. Compruebe siempre la existencia de errores y realice los ajustes necesarios.
* Tenga en cuenta que no se puede deshacer una acción. Para eliminar actividades pegadas, deberá seleccionarlas y eliminarlas. Por lo tanto, asegúrese de seleccionar solo las actividades que necesita antes de copiarlas.
* Puede copiar actividades de cualquier viaje, incluso las que están en sólo lectura.
* Puede seleccionar cualquier actividad, incluso aquellas que no estén vinculadas. Las actividades vinculadas permanecerán vinculadas después de pegarlas.

A continuación se indican los pasos para copiar/pegar actividades:

1. Abra un viaje.
1. Para seleccionar las actividades que desea copiar, mueva el ratón mientras hace clic. También puede hacer clic en cada actividad mientras pulsa la tecla **Ctrl/Comando** . Utilice **Ctrl/Comando + A** si desea seleccionar todas las actividades.
   ![](../assets/copy-paste1.png)
1. Pulse **Ctrl/Comando + C**.
Si solo desea copiar una actividad, puede hacer clic en ella y utilizar el icono **Copiar** en la parte superior izquierda del panel de configuración de la actividad.
   ![](../assets/copy-paste2.png)
1. En cualquier viaje, pulse **Ctrl/Comando + V** para pegar las actividades sin vincularlas a un nodo existente. Las actividades pegadas se colocan en el mismo orden. Después de pegarlas, las actividades permanecen seleccionadas para que pueda moverlas fácilmente. También puede colocar el cursor en un marcador de posición vacío y pulsar **Ctrl/Comando + V**. Las actividades pegadas se vincularán al nodo.
   ![](../assets/copy-paste3.png)

