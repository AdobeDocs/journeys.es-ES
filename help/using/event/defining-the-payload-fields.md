---
product: adobe campaign
title: Definición de los campos de carga útil
description: Obtenga información sobre cómo definir los campos de carga útil
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 3%

---

# Definición de los campos de carga útil {#concept_yrw_3qt_52b}



>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


La definición de carga útil permite elegir la información que el sistema espera recibir del evento en su recorrido y la clave para identificar a qué persona está asociada al evento. La carga útil se basa en la definición del campo XDM de Experience Cloud. Para obtener más información sobre XDM, consulte [esta página](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es).

1. Seleccione un esquema XDM de la lista y haga clic en el campo **[!UICONTROL Payload]** o en el icono **[!UICONTROL Edit]**.

   ![](../assets/journey8.png)

   Se muestran todos los campos definidos en el esquema. La lista de campos varía según el esquema. Puede buscar un campo específico o utilizar los filtros para mostrar todos los nodos y campos o solo los campos seleccionados. Según la definición del esquema, algunos campos pueden ser obligatorios y preseleccionados. No puede anular su selección. Todos los campos obligatorios para que Journey Orchestration reciba el evento correctamente están seleccionados de forma predeterminada.

   >[!NOTE]
   >
   >Asegúrese de haber agregado la mezcla &quot;orquestación&quot; al esquema XDM. Esto garantizará que el esquema contenga toda la información necesaria para trabajar con [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Seleccione los campos que espera recibir del evento. Estos son los campos que el usuario empresarial aprovechará en el recorrido. También deben incluir la clave que se utilizará para identificar a la persona asociada al evento (consulte [esta página](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Para los eventos generados por el sistema, el campo **[!UICONTROL eventID]** se agrega automáticamente a la lista de campos seleccionados para que [!DNL Journey Orchestration] pueda identificar el evento. El sistema que impulsa el evento no debe generar un ID, debe utilizar el que está disponible en la previsualización de carga útil. Consulte [esta página](../event/previewing-the-payload.md).

1. Cuando termine de seleccionar los campos necesarios, haga clic en **[!UICONTROL Save]** o presione **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   El número de campos seleccionados aparece en el campo **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
