---
product: adobe campaign
solution: Journey Orchestration
title: Definición de los parámetros del mensaje
description: Obtenga información sobre cómo definir los parámetros del mensaje
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Definición de los parámetros del mensaje {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

En la sección **[!UICONTROL Message parameters]**, pegue un ejemplo de la carga útil JSON para enviarla al servicio externo.

![](../assets/customactionpayloadmessage.png)

Podrá definir el tipo de parámetro (por ejemplo: cadena, entero, etc.).

También tendrá la opción de especificar si un parámetro es una constante o una variable:

* Constante significa que el valor del parámetro se define en el panel de configuración de la acción por una persona técnica. El valor será siempre el mismo en todos los viajes. No variará y el especialista en marketing no lo verá cuando utilice la acción personalizada en el viaje. Podría ser, por ejemplo, un ID que el sistema de terceros espera. En ese caso, el campo a la derecha de la constante o variable de alternancia es el valor pasado.
* Variable significa que el valor del parámetro variará. El comerciante que utilice esta acción personalizada en un viaje podrá pasar el valor que desee o especificar dónde recuperar el valor para este parámetro (por ejemplo, desde el evento, desde el Adobe Experience Platform, etc.). En ese caso, el campo a la derecha de la constante o variable de alternancia es la etiqueta que el especialista en mercadotecnia verá en el viaje para nombrar este parámetro.

![](../assets/customactionpayloadmessage2.png)
