---
title: Construcción del recorrido
description: Aprenda a construir un viaje sencillo en el caso de uso
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
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 5%

---


# Construcción del recorrido{#concept_eyw_mcy_w2b}

El usuario **** empresarial ahora puede construir el viaje. Nuestro viaje sólo incluirá un camino con las siguientes actividades:

* el SpaBeacon **[!UICONTROL Event]**: cuando una persona camina cerca de la señalización del spa, el sistema recibirá un evento y el viaje será inicio para esa persona.
* una **[!UICONTROL Condition]** actividad para comprobar que la persona es una mujer
* una **[!UICONTROL Email]** actividad (con Adobe Campaign Standard)
* una actividad **[!UICONTROL End]**

>[!NOTE]
>
>Las actividades **[!UICONTROL Push]** y **[!UICONTROL Email]** solo están disponibles en la paleta si tiene Adobes Campaign Standard.

Para obtener información adicional sobre cómo construir un viaje, consulte [](../building-journeys/journey.md).

1. En el menú superior, haga clic en la **[!UICONTROL Home]** ficha y **[!UICONTROL Create]** cree un nuevo viaje.

   ![](../assets/journey31.png)

1. Edite las propiedades del viaje en el panel de configuración que se muestra en el lado derecho. Lo llamamos &quot;viaje Spa&quot; y lo ponemos a durar un mes, del 1 al 31 de diciembre.

   ![](../assets/journeyuc1_8.png)

1. Inicio de diseñar su viaje arrastrando y soltando el evento &quot;SpaBeacon&quot; de la paleta al lienzo. También puede hacer clic con el botón doble en el evento de la paleta para agregarlo al lienzo.

   ![](../assets/journeyuc1_9.png)

1. Ahora agreguemos una condición para verificar que la persona es una mujer. Arrastre y suelte una actividad de condición en el viaje.

   ![](../assets/journeyuc1_10.png)

1. Elija el **[!UICONTROL Data Source Condition]** tipo y haga clic en el **[!UICONTROL Expression]** campo. También puede definir una etiqueta de condición que aparecerá en la flecha, en el lienzo.

   ![](../assets/journeyuc1_11.png)

1. Con el editor de expresiones simple, busque el campo de sexo (_persona > sexo_) y suéltelo a la derecha para crear la siguiente condición: &quot;el sexo es igual a &quot;mujer&quot;.

   ![](../assets/journeyuc1_12.png)

1. Suelte una **[!UICONTROL Email]** actividad y seleccione la plantilla de mensajería transaccional &quot;Descuento de spa&quot;. Esta plantilla se diseñó con Adobe Campaign. Consulte [esta página](https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

   ![](../assets/journeyuc1_13.png)

1. Haga clic dentro del **[!UICONTROL Email]** campo y seleccione la dirección de correo electrónico del origen de datos.

   ![](../assets/journeyuc1_14.png)

1. Del mismo modo, defina los campos de personalización de nombre y apellidos del origen de datos.

   ![](../assets/journeyuc1_15.png)

1. Suelte una **[!UICONTROL End]** actividad.

   ![](../assets/journeyuc1_17.png)

1. Haga clic en el **[!UICONTROL Test]** botón de alternancia y pruebe el viaje con perfiles de prueba. Si hay algún error, desactive el modo de prueba, modifique el viaje y pruébelo de nuevo. For more information on the test mode, refer to [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Cuando la prueba sea concluyente, puede publicar el viaje desde el menú desplegable superior derecho.

   ![](../assets/journeyuc1_18.png)

La próxima vez que una mujer camine cerca de la señalización del spa, recibirá inmediatamente un correo electrónico personalizado con el &quot;descuento del spa&quot;.
