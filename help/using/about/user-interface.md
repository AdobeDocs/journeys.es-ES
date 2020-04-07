---
title: La interfaz de usuario
description: Más información sobre la interfaz de usuario
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Interfaz de usuario{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Para sacar el máximo partido a la orquestación de viajes, recomendamos utilizar Chrome como navegador de Internet.
>
>Esta documentación se actualiza con frecuencia para reflejar los cambios recientes en el producto. Sin embargo, algunas capturas de pantalla pueden diferir ligeramente de la interfaz del producto.

## Acceso a la orquestación de viajes{#accessing_journey_orchestration}

Para acceder a la interfaz de la orquestación de viajes, haga clic en el icono **[!UICONTROL App Selector]** , en la parte superior derecha. A continuación, haga clic **[!UICONTROL Journey Orchestration]**, en la parte derecha, debajo de &quot;Plataforma de experiencia&quot;.

![](../assets/journey1.png)

También puede acceder a la orquestación de viajes desde la página de inicio de Experience Cloud, en la **[!UICONTROL Quick access]** sección .

![](../assets/journey1bis.png)

## Descubrimiento de la interfaz{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Acerca de la lista de viajes"
>abstract="La lista de viaje le permite realizar vistas de todos sus viajes a la vez, ver su estado y realizar acciones básicas. Puede duplicado, detener o eliminar sus viajes. Según el viaje, es posible que algunas acciones no estén disponibles. Por ejemplo, no se puede eliminar ni reiniciar un viaje terminado. Puede crear una nueva versión a partir de ella o duplicado la misma. También puede utilizar la barra de búsqueda para buscar un viaje."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Ver vídeo de demostración"

Los menús superiores le permiten navegar por las diferentes funcionalidades de la orquestación de viajes: **[!UICONTROL Home]**(los viajes),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Haga clic en el ![](../assets/icon-context.png) icono en la esquina superior derecha de la pantalla para mostrar la ayuda contextual. Está disponible en las distintas pantallas de lista de orquestación de viajes (viajes, eventos, acciones y fuentes de datos). Esto le permite realizar una vista rápida de la funcionalidad actual y acceder a los artículos y vídeos relacionados.

![](../assets/journey2bis.png)

## Búsqueda y filtrado{#section_lgm_hpz_pgb}

En las **[!UICONTROL Home]** listas,**[!UICONTROL Data Sources]****[!UICONTROL Events]** y **[!UICONTROL Actions]** , una barra de búsqueda permite buscar un elemento.

Se **[!UICONTROL Filters]** puede acceder al mismo haciendo clic en el icono de filtro en la parte superior izquierda de la lista. El menú filtros permite filtrar los elementos mostrados según diferentes criterios. Puede elegir mostrar únicamente los elementos de un determinado tipo o estado, los que ha creado o los modificados en los últimos 30 días.

En las **[!UICONTROL Data Sources]** listas, **[!UICONTROL Events]** y **[!UICONTROL Actions]** , utilice los filtros **de** creación para filtrar la fecha de creación y el usuario. Puede elegir, por ejemplo, mostrar solo los eventos creados en los últimos 30 días.

En la lista del viaje (debajo **[!UICONTROL Home]**), además del **[!UICONTROL Creation filters]**, también puede filtrar los viajes mostrados según su estado y versión (**[!UICONTROL Status and version filters]**). También puede elegir mostrar únicamente los viajes que utilizan un evento, un grupo de campos o una acción en particular (**[!UICONTROL Activity filters]** y **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** Permite seleccionar una fecha de publicación o un usuario. Puede elegir, por ejemplo, mostrar solo las versiones más recientes de viajes en directo que se publicaron ayer. Consulte [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Tenga en cuenta que las columnas mostradas se pueden personalizar mediante el botón de configuración en la parte superior derecha de las listas. La personalización se guarda para cada usuario.

Las **[!UICONTROL Last update]** columnas y **[!UICONTROL Last update by]** permiten mostrar cuándo se ha producido la última actualización de los viajes y qué usuario lo ha hecho.

![](../assets/journey74.png)

En los paneles evento, fuente de datos y configuración de acciones, el campo muestra el número de viajes que utilizan ese evento, grupo de campos o acción en particular. **[!UICONTROL Used in]** Puede hacer clic en el **[!UICONTROL View journeys]** botón para mostrar la lista de los viajes correspondientes.

![](../assets/journey3bis.png)

En las diferentes listas, puede realizar acciones básicas en cada elemento. Por ejemplo, puede duplicado o eliminación de un elemento.

![](../assets/journey4.png)

## Navegación a través de los campos de la plataforma de datos {#friendly-names-display}

Al definir la carga útil [de](../event/defining-the-payload-fields.md)evento, la carga útil [de grupo de](../datasource/field-groups.md) campos y seleccionar los campos en el editor [de](../expression/expressionadvanced.md)expresiones, se muestra el nombre para mostrar además del nombre del campo. Esta información se recupera de la definición de esquema del modelo de datos de experiencia.

Si se proporcionan descriptores como &quot;xdm:alternativoDisplayInfo&quot; al configurar esquemas, los nombres descriptivos reemplazarán a los nombres para mostrar. Resulta especialmente útil cuando se trabaja con &quot;eVars&quot; y campos genéricos.Puede configurar descriptores de nombres prácticos mediante una llamada de API. Para obtener más información, consulte la guía para desarrolladores de [Esquema Registry](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html).

![](../assets/xdm-from-descriptors.png)

Si hay un nombre descriptivo disponible, el campo se mostrará como `<friendly-name>(<name>)`. Si no hay ningún nombre descriptivo disponible, aparecerá el nombre para mostrar, por ejemplo `<display-name>(<name>)`. Si no se define ninguno de ellos, solo se mostrará el nombre técnico del campo `<name>`.

>[!NOTE]
>
>Los nombres descriptivos no se recuperan al seleccionar campos de una unión de esquemas.

## Uso de los distintos métodos abreviados{#section_ksq_zr1_ffb}

Estos son los diferentes métodos abreviados disponibles en la interfaz de la orquestación de viajes.

_En lista de viajes, acciones, fuentes de datos o eventos:_

* Pulse **c** para crear un nuevo viaje, acción, fuente de datos o evento.

_Al configurar una actividad en un viaje:_

El lienzo se guarda automáticamente. Puede ver, en la parte superior izquierda del lienzo, el estado de almacenamiento.

* Pulse **escape** para cerrar el panel de configuración y descartar los cambios realizados. Este es el equivalente del **[!UICONTROL Cancel]** botón.
* Pulse **[!UICONTROL Enter]** o haga clic fuera del panel para cerrar el panel de configuración. Los cambios se guardan. Este es el equivalente del **[!UICONTROL Ok]** botón.
* Si pulsa **[!UICONTROL Delete]** o **retroceso**, puede pulsar **[!UICONTROL Enter]** para confirmar la eliminación.

_En ventanas emergentes:_

* Pulse **escape** para cerrarlo (equivalente al botón **Cancelar** ).
* Pulse **[!UICONTROL Enter]** para guardar o confirmar (equivalente al **[!UICONTROL Ok]** botón o **[!UICONTROL Save]** ).

_En el panel de configuración evento, fuente de datos o acción:_

* Pulse **escape** para cerrar el panel de configuración sin guardar.
* Pulse **[!UICONTROL Enter]** para guardar las modificaciones y cerrar el panel de configuración.
* Pulse la **ficha** para saltar entre los distintos campos para configurarlos.

_En el editor de expresiones simple_

* Haga clic con el Doble en un campo, a la izquierda, para agregar una consulta (equivalente a arrastrar y soltar).

_Al explorar los campos XDM:_

* Al marcar un &quot;nodo&quot; se seleccionarán todos los campos del nodo.

_En todas las áreas de texto:_

* Utilice la combinación de **teclas Ctrl/Comando + A** para seleccionar el texto. En la previsualización de carga útil, selecciona la carga útil.

_En una pantalla con una barra de búsqueda:_

* Utilice la combinación de teclas **Ctrl/Comando + F** para seleccionar la barra de búsqueda.

_En el lienzo de un viaje:_

* Utilice la combinación de **teclas Ctrl/Comando + A** para seleccionar todas las actividades.
* Cuando se seleccionan una o varias actividades, presione **[!UICONTROL Delete]** o **retroceso** para eliminarlas. A continuación, puede pulsar **[!UICONTROL Enter]** para confirmar en la ventana emergente de confirmación.
* Haga clic con el botón Doble en una actividad desde la paleta izquierda para agregarla en la primera posición disponible (de arriba abajo).
