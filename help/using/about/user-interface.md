---
product: adobe campaign
title: Interfaz de usuario
description: Más información sobre la interfaz de usuario
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 93%

---

# Interfaz de usuario{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Para sacar el máximo partido a [!DNL Journey Orchestration], recomendamos utilizar Chrome como navegador de Internet. La interfaz se muestra en el idioma definido en IMS. Si el idioma de IMS no es compatible con [!DNL Journey Orchestration], la interfaz se muestra en inglés.
>
>Esta documentación se actualiza con frecuencia para reflejar los cambios recientes en el producto. Sin embargo, algunas capturas de pantalla pueden diferir ligeramente de la interfaz del producto.

## Acceso a [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Para acceder a la [!DNL Journey Orchestration]La interfaz de , haga clic en el botón **[!UICONTROL App Selector]** , en la parte superior derecha, haga clic en **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

También puede acceder a [!DNL Journey Orchestration]desde la página de inicio de Experience Cloud, en **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## Descubrimiento de la interfaz{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Acerca de la lista de recorridos"
>abstract="La lista de recorridos le permite realizar vistas de todos sus recorridos a la vez, ver su estado y realizar acciones básicas."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Ver vídeo de demostración"

Los menús superiores le permiten navegar por las diferentes funcionalidades de [!DNL Journey Orchestration]: **[!UICONTROL Home]**(los recorridos),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Haga clic en ![](../assets/icon-context.png), en la esquina superior derecha de la pantalla para mostrar la ayuda contextual. Está disponible en las distintas pantallas de lista de [!DNL Journey Orchestration] (recorridos, eventos, acciones y fuentes de datos). Esto le permite realizar una vista rápida de la funcionalidad actual y acceder a los artículos y vídeos relacionados.

![](../assets/journey2bis.png)

## Búsqueda y filtrado{#section_lgm_hpz_pgb}

En las listas **[!UICONTROL Home]**,**[!UICONTROL Data Sources]**,**[!UICONTROL Events]** y **[!UICONTROL Actions]** , una barra de búsqueda permite buscar un elemento.

Se puede acceder a **[!UICONTROL Filters]** haciendo clic en el icono de filtro en la parte superior izquierda de la lista. El menú filtros permite filtrar los elementos mostrados según diferentes criterios. Puede elegir mostrar únicamente los elementos de un determinado tipo o estado, los que ha creado o los modificados en los últimos 30 días.

En las listas **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** y **[!UICONTROL Actions]** , use **[!UICONTROL Creation filters]** para filtrar la fecha de creación y el usuario. Puede elegir, por ejemplo, mostrar solo los eventos creados en los últimos 30 días.

En la lista de recorridos (debajo de **[!UICONTROL Home]**), además del **[!UICONTROL Creation filters]**, también puede filtrar los recorridos mostrados según su estado, tipo y versión (**[!UICONTROL Status and version filters]**). El tipo puede ser: **[!UICONTROL Unitary event]** o **[!UICONTROL Segment qualification]**. También puede elegir mostrar únicamente los recorrido que utilizan un evento, un grupo de campos o una acción en particular (**[!UICONTROL Activity filters]** y **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** Permite seleccionar una fecha de publicación o un usuario. Puede elegir, por ejemplo, mostrar solo las versiones más recientes de recorridos en directo que se publicaron ayer. Consulte [esta página](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Tenga en cuenta que las columnas mostradas se pueden personalizar mediante el botón de configuración en la parte superior derecha de las listas. La personalización se guarda para cada usuario.

Las columnas **[!UICONTROL Last update]** y **[!UICONTROL Last update by]** permiten mostrar cuándo se ha producido la última actualización de los recorridos y qué usuario lo ha hecho.

![](../assets/journey74.png)

En los paneles evento, fuente de datos y configuración de acciones, el campo muestra el número de recorridos que utilizan ese evento, grupo de campos o acción en particular. **[!UICONTROL Used in]** Puede hacer clic en **[!UICONTROL View journeys]** para mostrar la lista de los recorridos correspondientes.

![](../assets/journey3bis.png)

En las diferentes listas, puede realizar acciones básicas por cada elemento. Por ejemplo, puede duplicar o eliminar un elemento.

![](../assets/journey4.png)

## Navegación por los campos de Adobe Experience Platform {#friendly-names-display}

Al definir la [carga útil de evento](../event/defining-the-payload-fields.md), la [carga útil de grupo de campos](../datasource/field-groups.md) y seleccionar los campos en el [editor de expresiones](../expression/expressionadvanced.md), se muestra el nombre para mostrar además del nombre del campo. Esta información se recupera de la definición de esquema del modelo de datos de Experience.

Si se proporcionan descriptores como &quot;xdm:alternateDisplayInfo&quot; al configurar esquemas, los nombres descriptivos reemplazarán los nombres para mostrar. Resulta especialmente útil cuando se trabaja con &quot;eVars&quot; y campos genéricos. Puede configurar descriptores de nombres prácticos mediante una llamada API. Para obtener más información, consulte la [Guía para desarrolladores de Schema Registry](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=es).

![](../assets/xdm-from-descriptors.png)

Si hay un nombre descriptivo disponible, el campo se mostrará como `<friendly-name>(<name>)`. Si no hay ningún nombre descriptivo disponible, aparecerá el nombre para mostrar, por ejemplo `<display-name>(<name>)`. Si no se define ninguno de ellos, solo se mostrará el nombre técnico del campo `<name>`.

>[!NOTE]
>
>Los nombres descriptivos no se recuperan al seleccionar campos de una unión de esquemas.

## Accesibilidad{#accessibility}

Adobe Experience Platform proporciona las funciones de accesibilidad de Adobe Journey Optimizer:

* Accesibilidad del teclado
* Contraste de color
* Validación de campos obligatorios

[Más información](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=es){target="_blank"} en la documentación de Adobe Experience Platform.

Puede utilizar estos métodos abreviados del teclado comunes en Adobe Journey Optimizer:

| Acción | Acceso directo |
| --- | --- |
| Desplazamiento entre elementos, secciones y grupos de menús de la interfaz de usuario | Tabulación |
| Retroceder entre elementos, secciones y grupos de menús de la interfaz de usuario | Mayús + Tab |
| Desplazarse dentro de las secciones para definir el enfoque en elementos individuales | Flecha |
| Seleccionar o borrar un elemento que esté enfocado | Intro o barra espaciadora |
| Cancelar una selección, contraer un panel o cerrar un cuadro de diálogo | ESC |

[Más información](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html?lang=es){target="_blank"} en la documentación de Adobe Experience Platform.

Puede utilizar estos métodos abreviados en partes específicas de Journey Optimizer:

<table>
  <thead>
    <tr>
      <th>Elemento de interfaz</th>
      <th>Acción</th>
      <th>Acceso directo</th>
    </tr>
  </thead>
  <tr>
    <td>Lista de recorridos, acciones, fuentes de datos o eventos</td>
    <td>Crear un recorrido, una acción, una fuente de datos o un evento</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Lienzo de recorrido en estado de borrador</td>
    <td>Añadir una actividad de la paleta izquierda en la primera posición disponible, de arriba a abajo</td>
    <td>Doble clic en la actividad</td>
  </tr>
  <tr>
    <td>Seleccionar todas las actividades</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
  <tr>
    <td>Eliminación de las actividades seleccionadas</td>
    <td>Use la tecla Suprimir o Retroceso y a continuación Intro para confirmar la eliminación</td>
  </tr>
  <tr>
  <td rowspan="3">

Panel de configuración de estos elementos:

<ul>
  <li>Actividad en un recorrido</li>
  <li>Evento</li>
  <li>Fuente de datos</li>
  <li>Acción</li>
</ul>

</td>
    <td>Mover al campo siguiente que se va a configurar</td>
    <td>Tabulación</td>
  </tr>
  <tr>
    <td>Guarde los cambios y cierre el panel de configuración</td>
    <td>Intro</td>
  </tr>
  <tr>
    <td>Descartar cambios y cerrar el panel de configuración</td>
    <td>ESC</td>
  </tr>
  <tr>
    <td rowspan="4">Recorrido en modo de prueba</td>
    <td>Habilitar o deshabilitar el modo de prueba</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Activa un evento en un recorrido basado en eventos</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Activa un evento en un recorrido basado en segmentos para el cual la opción **[!UICONTROL Single profile at a time]** está activada

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Mostrar los registros de prueba</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Campo de texto</td>
    <td>Seleccionar todo el texto del campo seleccionado</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Ventana emergente</td>
    <td>Guardar los cambios o confirmar la acción</td>
    <td>Intro</td>
  </tr>
  <tr>
    <td>Cerrar la ventana</td>
    <td>ESC</td>
  </tr>
  <tr>
    <td>Editor de expresiones simples</td>
    <td>Seleccionar y añadir un campo</td>
    <td>Doble clic en un campo</td>
  </tr>
  <tr>
    <td>Explorar los campos XDM</td>
    <td>Seleccionar todos los campos de un nodo</td>
    <td>Seleccionar el nodo principal</td>
  </tr>
  <tr>
    <td>Vista previa de carga útil</td>
    <td>Seleccionar la carga útil</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
</table>
