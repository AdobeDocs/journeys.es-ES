---
title: Eventos basados en reglas
description: Obtenga más información sobre los eventos basados en reglas.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 11%

---


# Eventos basados en reglas{#simplified-events}

Hemos simplificado la forma de configurar el Evento de Experience. Presentamos un nuevo método que no requiere el uso de un ID de evento. Al configurar el evento en Journey Orchestration, ahora puede definir un evento basado en reglas.

Este nuevo tipo de evento no genera un eventID. Con el simple editor de expresiones, ahora simplemente define una regla que utilizará el sistema para identificar los eventos relevantes que activarán sus viajes. Esta regla se puede basar en cualquier campo disponible en la carga útil de evento, por ejemplo la ubicación del perfil o el número de elementos agregados al carro de perfiles.

Este nuevo método es mayormente transparente para los usuarios. El único cambio es un nuevo campo en la pantalla de definición de evento.

>[!CAUTION]
>
>Se define una regla de límite para eventos basados en reglas. Limita el número de eventos cualificados que un viaje puede procesar a 400 k por minuto. Para obtener más información, póngase en contacto con el punto de contacto del programa Alfa.

## Aprovechamiento de los datos de Adobe Analytics{#analytics-data}

>[!NOTE]
>
>Esta sección solo se aplica a los clientes que necesiten utilizar datos de Adobe Analytics.

Puede aprovechar todos los datos de evento de comportamiento de Adobe Analytics que ya está capturando y transmitiendo a la plataforma para activar viajes y automatizar experiencias para sus clientes.

Para que esto funcione, debe activar, en Adobe Experience Platform, el grupo de informes que desea aprovechar:

1. En Adobe Experience Platform, seleccione **[!UICONTROL Sources]** luego **[!UICONTROL Add data]** en la sección Adobe Analytics. Se muestra la lista de los grupos de informes de Adobe Analytics disponibles.

1. Elija el grupo de informes que desee habilitar, haga clic en **[!UICONTROL Next]** y luego en **[!UICONTROL Finish]**.

1. Comparta el ID de datos de origen con el punto de contacto del programa alfa.

Esto habilita el conector de origen de Analytics para ese grupo de informes. Cada vez que entran los datos, se transforman en un evento de experiencias y se envían a Adobe Experience Platform.

![](../assets/alpha-event9.png)

Para obtener más información sobre el conector de origen de Adobe Analytics, consulte la [documentación](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) y el [tutorial](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).

## Configuración de un evento basado en reglas{#configuring-rule-based}

1. En el menú de la izquierda, haga clic en el **[!UICONTROL Admin]** icono y, a continuación, haga clic en **[!UICONTROL Events]**. Se muestra la lista de eventos.

   ![](../assets/alpha-event1.png)

1. Haga clic en **[!UICONTROL Add]** para crear un nuevo evento. El panel de configuración de evento se abre en el lado derecho de la pantalla.

   ![](../assets/alpha-event2.png)

1. Escriba el nombre del evento. También puede agregar una descripción.

   ![](../assets/alpha-event3.png)

1. In the new **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >El **[!UICONTROL System Generated]** tipo es el método existente que requiere un eventID. Consulte [esta sección](../event/about-events.md).

1. Defina la carga útil **[!UICONTROL Schema]** y **[!UICONTROL Fields]**. Consulte [esta sección](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Al seleccionar el **[!UICONTROL System Generated type]**, solo están disponibles los esquemas que tienen la mezcla de tipo eventID. Cuando selecciona el **[!UICONTROL Rule Based]** tipo, están disponibles todos los esquemas de Experience Evento.

1. Haga clic dentro del **[!UICONTROL Event ID condition]** campo. Con el editor de expresiones simple, defina la condición que utilizará el sistema para identificar los eventos que activarán el viaje.

   ![](../assets/alpha-event6.png)

   En nuestro ejemplo, escribimos una condición basada en la ciudad del perfil. Esto significa que cada vez que el sistema recibe un evento que coincide con esta condición (**[!UICONTROL City]** campo y **[!UICONTROL Paris]** valor), lo pasa al Journey Orchestration.

1. Defina el **[!UICONTROL Namespace]** y **[!UICONTROL Key]**. Consulte [Selección de la Área de nombres](../event/selecting-the-namespace.md) y [Definición de la clave](../event/defining-the-event-key.md)de evento.

   ![](../assets/alpha-event7.png)

Los demás pasos para la configuración del evento y la creación del viaje permanecen sin cambios.

El evento está ahora configurado y listo para ser lanzado en un viaje como cualquier otro evento. Cada vez que se envía al sistema un evento que coincide con la regla, se pasa al Journey Orchestration para activar los viajes.

## Modo de prueba para eventos basados en reglas{#test-rule-based}

El modo de prueba también está disponible para viajes que utilizan un evento basado en reglas.

Al activar un evento, la pantalla de configuración **de** Evento le permite definir los parámetros de evento que se van a pasar en la prueba. Puede realizar la vista de la condición de ID de evento haciendo clic en el icono de información sobre herramientas en la esquina superior derecha. También hay disponible una información sobre herramientas junto a cada campo que forme parte de la evaluación de reglas.

![](../assets/alpha-event8.png)

Para obtener más información sobre cómo utilizar el modo de prueba, consulte [esta página](../building-journeys/testing-the-journey.md).
