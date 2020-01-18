---
title: Grupos de campo
description: Información sobre los grupos de campos
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Grupos de campo {#concept_ntl_ypt_52b}

## Definición de grupos de campos {#section_dsz_kjd_fjb}

Para cada origen de datos, puede definir varios grupos de campos, cada uno de ellos con una duración de caché específica. Permiten elegir los campos que se recuperarán del origen de datos que se utilizarán en los viajes.

Por ejemplo, puede crear un grupo de campos con el número de teléfono, el correo electrónico, el nombre y la dirección del perfil. Luego podrá usar estos datos en su viaje para crear condiciones. Por ejemplo, puede decidir enviar un SMS solo si el número de teléfono del perfil no está vacío. Si está vacío, puede enviar un correo electrónico.

Aunque se añada automáticamente un nombre predeterminado, se recomienda que asigne un nombre al grupo de campos. De hecho, el nombre del grupo de campos será visible para otros usuarios en la orquestación de viajes. Es recomendable asignar un nombre relevante a los grupos de campos.

Cuando se utiliza un campo de origen de datos en un viaje, el sistema recuperará todos los campos definidos para ese grupo de campos. Por lo tanto, es recomendable seleccionar solo los campos que necesita para sus viajes. Esto reducirá la latencia de la solicitud en sus viajes, aumentando así el rendimiento. Tenga en cuenta que puede agregar fácilmente más campos en grupos de campos más adelante.

**[!UICONTROL Cache duration]**también es importante, ya que le ayudará a optimizar el rendimiento. La duración de la caché significa que, en un viaje, si los datos de un grupo de campos se recuperan una vez, el sistema los almacenará temporalmente en caché. Si se requieren los mismos datos más adelante en el mismo viaje, el sistema no realizará otra solicitud al origen de datos. La configuración de la duración de la caché debe adaptarse para cada caso de uso. Si necesita recuperar datos en tiempo real como el estado de la reserva del hotel, la información del tiempo o el número de puntos de lealtad, asociará el grupo de campos que contiene estos campos con una corta duración de la caché (por ejemplo, 1 segundo). Para los campos que se actualizan con menos frecuencia (nombre, sexo), creará un segundo grupo de campos con una duración de caché mayor (por ejemplo, 5 días).

El número de viajes que utilizan un grupo de campos se muestra en el **[!UICONTROL Used in]**campo. Puede hacer clic en el**[!UICONTROL View journeys]** botón para mostrar la lista de viajes con este grupo de campos.

>[!NOTE]
>
>Tenga en cuenta que si un grupo de campos no tiene ningún campo, no se mostrará en el editor de expresiones.

![](../assets/journey3bis.png)

## Ciclo de vida del grupo de campos {#section_abk_njd_fjb}

Puede agregar o quitar campos de un grupo de campos que no se utilicen en ningún borrador o viaje en directo.

Puede agregar un campo, pero no puede quitarlo de un grupo de campos utilizado en uno o varios viajes en borrador o en directo. Esto evitará romper los viajes.

Para eliminar un campo de un grupo de campos utilizado en uno o varios viajes, siga estos pasos. Veamos un ejemplo de un grupo de campos llamado &quot;Grupo de campos A&quot;.

1. En la lista de grupos de campos, coloque el cursor en &quot;Grupo de campos A&quot; y haga clic en el icono situado a la derecha **[!UICONTROL Duplicate]**. Asigne un nombre al grupo de campos duplicado &quot;Grupo de campos B&quot;, por ejemplo.
1. En &quot;Grupo de campos B&quot;, elimine los campos que ya no desee.
1. En &quot;Grupo de campos A&quot;, compruebe dónde se utiliza este grupo de campos. Esta información se muestra en el **[!UICONTROL Used in]**campo.
1. Abra todos los viajes que utilicen &quot;Field Group A&quot;.
1. Cree nuevas versiones de cada uno de estos viajes. Edite todas las actividades con &quot;Grupo de campos A&quot; y seleccione &quot;Grupo de campos B&quot;.
1. Detenga las versiones anteriores de viajes que utilicen &quot;Field Group A&quot;. Entonces no debería realizar ningún viaje con &quot;Field Group A&quot;.
1. Elimine &quot;Grupo de campos A&quot; porque ya no se utiliza.
