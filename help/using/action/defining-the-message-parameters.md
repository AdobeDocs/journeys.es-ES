---
product: adobe campaign
solution: Journey Orchestration
title: Definición de los parámetros del mensaje
description: Obtenga información sobre cómo definir los parámetros del mensaje
feature: Recorridos
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Definición de los parámetros del mensaje {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

En la sección **[!UICONTROL Message parameters]** , pegue un ejemplo de la carga útil JSON para enviarla al servicio externo.

![](../assets/customactionpayloadmessage.png)

Puede definir el tipo de parámetro (p. ej.: string, integer, etc.).

También tendrá la opción de especificar si un parámetro es una constante o una variable:

* Constante significa que el valor del parámetro se define en el panel de configuración de acciones mediante un perfil técnico. El valor siempre será el mismo en todos los recorridos. No variará y el especialista en marketing no lo verá al utilizar la acción personalizada en el recorrido. Podría ser, por ejemplo, un ID que el sistema de terceros espera. En ese caso, el campo a la derecha de la constante o variable de alternancia es el valor pasado.
* Variable significa que el valor del parámetro variará. El especialista en marketing que utilice esta acción personalizada en un recorrido podrá pasar el valor que desee o especificar dónde recuperar el valor para este parámetro (por ejemplo, desde el evento, desde Adobe Experience Platform, etc.). En ese caso, el campo a la derecha de la constante o variable de alternancia es la etiqueta que el especialista en marketing verá en el recorrido para asignar un nombre a este parámetro.

![](../assets/customactionpayloadmessage2.png)
