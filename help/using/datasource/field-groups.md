---
product: adobe campaign
solution: Journey Orchestration
title: Grupos de campo
description: Información sobre los grupos de campos
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---



# Grupos de campo {#concept_ntl_ypt_52b}

Los grupos de campos son conjuntos de campos que se pueden recuperar de un origen de datos y utilizar en un viaje.

## Definición de grupos de campos {#section_dsz_kjd_fjb}

Para cada origen de datos, puede definir varios grupos de campos, cada uno de ellos con una duración de caché específica.

Por ejemplo, puede crear un grupo de campos con el número de teléfono, el correo electrónico, el nombre y la dirección del perfil. Luego podrá usar estos datos en su viaje para crear condiciones. Por ejemplo, puede decidir enviar un SMS solo si el número de teléfono del perfil no está vacío. Si está vacío, puede enviar un correo electrónico.

Aunque se añada automáticamente un nombre predeterminado, se recomienda que asigne un nombre al grupo de campos. De hecho, el nombre del grupo de campos será visible para otros usuarios de [!DNL Journey Orchestration]. Es recomendable asignar un nombre relevante a los grupos de campos.

Cuando se utiliza un campo de origen de datos en un viaje, el sistema recuperará todos los campos definidos para ese grupo de campos. Por lo tanto, es recomendable seleccionar solo los campos que necesita para sus viajes. Esto reducirá la latencia de la solicitud en sus viajes, aumentando así el rendimiento. Tenga en cuenta que puede agregar fácilmente más campos en grupos de campos más adelante.

**[!UICONTROL Cache duration]** también es importante, ya que le ayudará a optimizar el rendimiento. La duración de la caché significa que, en un viaje, si los datos de un grupo de campos se recuperan una vez, el sistema los almacenará temporalmente en caché. Si se requieren los mismos datos más adelante en el mismo viaje, el sistema no realizará otra solicitud al origen de datos. La configuración de la duración de la caché debe adaptarse para cada caso de uso. Si necesita recuperar datos en tiempo real como el estado de la reserva del hotel, la información del tiempo o el número de puntos de lealtad, asociará el grupo de campos que contiene estos campos con una corta duración de la caché (por ejemplo, 1 segundo). Para los campos que se actualizan con menos frecuencia (nombre, sexo), creará un segundo grupo de campos con una duración de caché mayor (por ejemplo, 5 días).

The number of journeys that use a field group is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of journeys using this field group.

>[!NOTE]
>
>Tenga en cuenta que si un grupo de campos no tiene ningún campo, no se mostrará en el editor de expresiones.

![](../assets/journey3bis.png)

## Ciclo de vida del grupo de campos {#section_abk_njd_fjb}

Puede agregar o quitar campos de un grupo de campos que no se utilicen en ningún borrador o viaje en directo.

Puede agregar un campo, pero no puede quitarlo de un grupo de campos utilizado en uno o varios viajes en borrador o en directo. Esto evitará romper los viajes.

Para eliminar un campo de un grupo de campos utilizado en uno o varios viajes, siga estos pasos. Veamos un ejemplo de un grupo de campos llamado &quot;Grupo de campos A&quot;.

1. En la lista de los grupos de campos, coloque el cursor en &quot;Grupo de campos A&quot; y haga clic en el **[!UICONTROL Duplicate]** icono situado a la derecha. Asigne un nombre al grupo de campos duplicado &quot;Grupo de campos B&quot;, por ejemplo.
1. En &quot;Grupo de campos B&quot;, elimine los campos que ya no desee.
1. En &quot;Grupo de campos A&quot;, compruebe dónde se utiliza este grupo de campos. Esta información se muestra en el **[!UICONTROL Used in]** campo.
1. Abra todos los viajes que utilicen &quot;Field Group A&quot;.
1. Cree nuevas versiones de cada uno de estos viajes. Edite todas las actividades utilizando &quot;Grupo de campos A&quot; y seleccione &quot;Grupo de campos B&quot;.
1. Detenga las versiones anteriores de viajes que utilicen &quot;Field Group A&quot;. Entonces no debería realizar ningún viaje con &quot;Field Group A&quot;.
1. Elimine &quot;Grupo de campos A&quot; porque ya no se utiliza.
