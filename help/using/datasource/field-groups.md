---
product: adobe campaign
title: Grupos de campo
description: Obtenga información sobre los grupos de campos
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 1%

---

# Grupos de campo {#concept_ntl_ypt_52b}

Los grupos de campos son conjuntos de campos que se pueden recuperar de un origen de datos y utilizar en un recorrido.

## Definición de grupos de campos {#section_dsz_kjd_fjb}

Para cada fuente de datos, se pueden definir varios grupos de campos.

Por ejemplo, puede crear un grupo de campos con el número de teléfono, el correo electrónico, el nombre y la dirección del perfil. A continuación, podrá utilizar estos datos en el recorrido para crear condiciones. Por ejemplo, puede decidir enviar un SMS solo si el número de teléfono del perfil no está vacío. Si está vacío, puede enviar un correo electrónico.

Aunque se añada automáticamente un nombre predeterminado, le recomendamos que asigne un nombre al grupo de campos. De hecho, el nombre del grupo de campos será visible para otros usuarios en [!DNL Journey Orchestration]. Es recomendable asignar un nombre relevante a los grupos de campos.

Cuando se utiliza un campo de origen de datos en un recorrido, el sistema recupera todos los campos definidos para ese grupo de campos. Por lo tanto, es recomendable seleccionar solo los campos que necesita para sus recorridos. Esto reducirá la latencia de las solicitudes en los recorridos, lo que aumenta el rendimiento. Tenga en cuenta que puede agregar fácilmente más campos en grupos de campos más adelante.

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
