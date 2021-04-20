---
product: adobe campaign
solution: Journey Orchestration
title: Grupos de campo
description: Obtenga información sobre los grupos de campos
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 0%

---



# Grupos de campo {#concept_ntl_ypt_52b}

Los grupos de campos son conjuntos de campos que se pueden recuperar de un origen de datos y utilizar en un recorrido.

## Definición de grupos de campos {#section_dsz_kjd_fjb}

Para cada fuente de datos, se pueden definir varios grupos de campos, cada uno con una duración específica de la caché.

Por ejemplo, puede crear un grupo de campos con el número de teléfono, el correo electrónico, el nombre y la dirección del perfil. A continuación, podrá utilizar estos datos en el recorrido para crear condiciones. Por ejemplo, puede decidir enviar un SMS solo si el número de teléfono del perfil no está vacío. Si está vacío, puede enviar un correo electrónico.

Aunque se añada automáticamente un nombre predeterminado, le recomendamos que asigne un nombre al grupo de campos. De hecho, el nombre del grupo de campos será visible para otros usuarios en [!DNL Journey Orchestration]. Es recomendable asignar un nombre relevante a los grupos de campos.

Cuando se utiliza un campo de origen de datos en un recorrido, el sistema recupera todos los campos definidos para ese grupo de campos. Por lo tanto, es recomendable seleccionar solo los campos que necesita para sus recorridos. Esto reducirá la latencia de las solicitudes en los recorridos, lo que aumenta el rendimiento. Tenga en cuenta que puede agregar fácilmente más campos en grupos de campos más adelante.

**[!UICONTROL Cache duration]** también es importante, ya que le ayudará a optimizar el rendimiento. La duración de la caché significa que en un recorrido, si los datos de un grupo de campos se recuperan una vez, el sistema los almacenará en caché temporalmente. Si se necesitan los mismos datos más adelante en el mismo recorrido, el sistema no realizará otra solicitud al origen de datos. La configuración de la duración de la caché debe adaptarse para cada caso de uso. Si necesita recuperar datos en tiempo real como el estado de reserva del hotel, la información meteorológica o el número de puntos de lealtad, asociará el grupo de campos que contiene estos campos con una breve duración de caché (1 segundo, por ejemplo). Para los campos que se actualizan con menos frecuencia (nombre, sexo), se crea un segundo grupo de campos con una duración de caché más larga (por ejemplo, 5 días).

El número de recorridos que utilizan un grupo de campos se muestra en el campo **[!UICONTROL Used in]**. Puede hacer clic en el botón **[!UICONTROL View journeys]** para mostrar la lista de recorridos que utilizan este grupo de campos.

>[!NOTE]
>
>Tenga en cuenta que si un grupo de campos no tiene ningún campo, no se mostrará en el editor de expresiones.

![](../assets/journey3bis.png)

## Ciclo de vida del grupo de campos {#section_abk_njd_fjb}

Puede agregar o quitar campos de un grupo de campos que no se utilice en ningún borrador o recorrido activo.

Puede agregar, pero no puede quitar un campo de un grupo de campos utilizado en uno o varios recorridos en borrador o activo. Esto evitará romper recorridos.

Para eliminar un campo de un grupo de campos utilizado en uno o varios recorridos, siga estos pasos. Veamos un ejemplo de un grupo de campos denominado &quot;Grupo de campos A&quot;.

1. En la lista de grupos de campos, coloque el cursor en &quot;Grupo de campos A&quot; y haga clic en el icono **[!UICONTROL Duplicate]** situado a la derecha. Asigne un nombre al grupo de campos duplicado &quot;Grupo de campos B&quot;, por ejemplo.
1. En &quot;Grupo de campos B&quot;, elimine los campos que ya no desee.
1. En &quot;Grupo de campos A&quot;, compruebe dónde se utiliza este grupo de campos. Esta información se muestra en el campo **[!UICONTROL Used in]**.
1. Abra todos los recorridos que utilicen &quot;Grupo de campos A&quot;.
1. Cree nuevas versiones de cada uno de estos recorridos. Edite todas las actividades utilizando &quot;Grupo de campos A&quot; y seleccione &quot;Grupo de campos B&quot;.
1. Detenga las versiones anteriores de los recorridos que utilizan &quot;Grupo de campos A&quot;. Por lo tanto, no debe tener ningún recorrido usando &quot;Grupo de campos A&quot;.
1. Elimine &quot;Grupo de campos A&quot; porque ya no se utiliza.
