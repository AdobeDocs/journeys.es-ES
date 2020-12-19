---
product: adobe campaign
solution: Journey Orchestration
title: Definición de los campos de carga útil
description: Obtenga información sobre cómo definir los campos de carga útil
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---


# Definición de los campos de carga útil {#concept_yrw_3qt_52b}

La definición de carga útil le permite elegir la información que el sistema espera recibir del evento en su viaje y la clave para identificar qué persona está asociada al evento. La carga útil se basa en la definición del campo XDM del Experience Cloud. Para obtener más información sobre XDM, consulte [esta página](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/home.html).

1. Seleccione un esquema XDM en la lista y haga clic en el campo **[!UICONTROL Payload]** o en el icono **[!UICONTROL Edit]**.

   ![](../assets/journey8.png)

   Se muestran todos los campos definidos en el esquema. La lista de los campos varía de un esquema a otro. Puede buscar un campo específico o utilizar los filtros para mostrar todos los nodos y campos o solo los campos seleccionados. Según la definición de esquema, algunos campos pueden ser obligatorios y estar preseleccionados. No se pueden anular las selecciones.

   >[!NOTE]
   >
   >Asegúrese de haber agregado la mezcla de &quot;orquestación&quot; al esquema XDM. Esto garantizará que su esquema contenga toda la información necesaria para trabajar con [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Seleccione los campos que espera recibir del evento. Estos son los campos que el usuario comercial aprovechará en el viaje. También deben incluir la clave que se utilizará para identificar a la persona asociada al evento (consulte [esta página](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Para eventos generados por el sistema, el campo **[!UICONTROL eventID]** se agrega automáticamente en la lista de campos seleccionados para que [!DNL Journey Orchestration] pueda identificar el evento. El sistema que empuja el evento no debe generar un ID, debe utilizar el disponible en la previsualización de carga útil. Consulte [esta página](../event/previewing-the-payload.md).

1. Cuando haya terminado de seleccionar los campos necesarios, haga clic en **[!UICONTROL Save]** o presione **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   El número de campos seleccionados aparece en el campo **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
