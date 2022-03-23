---
product: adobe campaign
title: 'Creación del recorrido: simple'
description: Aprenda a crear el recorrido de casos de uso simple
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 37%

---

# Construcción del recorrido{#concept_eyw_mcy_w2b}

El **usuario empresarial** ahora puede compilar el recorrido. Nuestro recorrido solo incluirá una ruta con las siguientes actividades:

* el &quot;SpaBeacon&quot; **[!UICONTROL Event]**: cuando una persona camina cerca de la señalización del spa, el sistema recibirá un evento y el recorrido comenzará para esa persona.
* a **[!UICONTROL Condition]** actividad para comprobar que la persona es una mujer
* an **[!UICONTROL Email]** actividad (con Adobe Campaign Standard)
* una actividad **[!UICONTROL End]**

>[!NOTE]
>
>Las actividades **[!UICONTROL Push]** y **[!UICONTROL Email]** solo están disponibles en la paleta si tiene Adobe Campaign Standard.

Para obtener información adicional sobre cómo crear un recorrido, consulte [esta página](../building-journeys/journey.md).

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Home]** y **[!UICONTROL Create]** para crear un nuevo recorrido.

   ![](../assets/journey31.png)

1. Edite las propiedades del recorrido en el panel de configuración que se muestra en el lado derecho. Lo llamamos &quot;recorrido Spa&quot; y lo configuramos para que dure un mes, del 1 al 31 de diciembre.

   ![](../assets/journeyuc1_8.png)

1. Para diseñar el recorrido, arrastre y suelte el evento &quot;SpaBeacon&quot; de la paleta al lienzo. También puede hacer doble clic en el evento de la paleta para agregarlo al lienzo.

   ![](../assets/journeyuc1_9.png)

1. Ahora vamos a agregar una condición para verificar que la persona es una mujer. Arrastre y suelte una actividad de condición en el recorrido.

   ![](../assets/journeyuc1_10.png)

1. Elija el tipo **[!UICONTROL Data Source Condition]** y haga clic en el campo **[!UICONTROL Expression]** . También puede definir una etiqueta de condición que aparecerá en la flecha del lienzo.

   ![](../assets/journeyuc1_11.png)

1. Con el editor de expresiones simple, busque el campo gender (_persona > sexo_) y suéltela a la derecha para crear la siguiente condición: &quot;el sexo es igual a &quot;Femenino&quot;.

   ![](../assets/journeyuc1_12.png)

1. Suelte un **[!UICONTROL Email]** y seleccione la plantilla de mensajería transaccional &quot;Descuento de spa&quot;. Esta plantilla se diseñó con Adobe Campaign. Consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=es).

   ![](../assets/journeyuc1_13.png)

1. Haga clic dentro del **[!UICONTROL Email]** y seleccione la dirección de correo electrónico de la fuente de datos.

   ![](../assets/journeyuc1_14.png)

1. Del mismo modo, defina los campos de personalización de nombre y apellido del origen de datos.

   ![](../assets/journeyuc1_15.png)

1. Suelte un **[!UICONTROL End]** actividad.

   ![](../assets/journeyuc1_17.png)

1. Haga clic en el **[!UICONTROL Test]** alterne y pruebe el recorrido con perfiles de prueba. Si hay algún error, desactive el modo de prueba, modifique el recorrido y pruebe de nuevo. Para obtener más información sobre el modo de prueba, consulte [esta página](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Cuando la prueba sea concluyente, puede publicar el recorrido del menú desplegable superior derecho.

   ![](../assets/journeyuc1_18.png)

La próxima vez que una mujer camine cerca de la señalización del spa, recibirá inmediatamente un correo electrónico personalizado de &quot;descuento en spa&quot;.
