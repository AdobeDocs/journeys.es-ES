---
title: Definición de los campos de carga útil
description: Obtenga información sobre cómo definir los campos de carga útil
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


# Definición de los campos de carga útil {#concept_yrw_3qt_52b}

La definición de carga útil permite elegir la información que el sistema espera recibir del evento en el viaje y la clave para identificar qué persona está asociada al evento. La carga útil se basa en la definición del campo XDM de Experience Cloud. For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Seleccione un esquema XDM de la lista y haga clic en el **[!UICONTROL Payload]**campo o en el**[!UICONTROL Edit]** icono.

   ![](../assets/journey8.png)

   Se muestran todos los campos definidos en el esquema. La lista de campos varía de un esquema a otro. Puede buscar un campo específico o utilizar los filtros para mostrar todos los nodos y campos o solo los campos seleccionados. Según la definición del esquema, algunos campos pueden ser obligatorios y estar preseleccionados. No se pueden anular las selecciones.

   >[!NOTE]
   >
   >Asegúrese de que ha agregado la combinación &quot;orquestación&quot; al esquema XDM. Esto garantizará que su esquema contenga toda la información necesaria para trabajar con la orquestación de viajes.

   ![](../assets/journey9.png)

1. Seleccione los campos que espera recibir del evento. Estos son los campos que el usuario comercial aprovechará en el viaje. También deben incluir la clave que se utilizará para identificar a la persona asociada al evento (consulte [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >El **[!UICONTROL eventID]**campo se agrega automáticamente a la lista de campos seleccionados para que la orquestación de viajes pueda identificar el evento. El sistema que impulsa el evento no debe generar un ID, debe utilizar el disponible en la vista previa de la carga útil. Consulte[](../event/previewing-the-payload.md).

1. Cuando haya terminado de seleccionar los campos necesarios, haga clic en **[!UICONTROL Save]**o presione**[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   El número de campos seleccionados aparece en el **[!UICONTROL Payload]**campo.

   ![](../assets/journey12.png)
