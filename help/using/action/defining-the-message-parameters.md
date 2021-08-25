---
product: adobe campaign
title: Definición de los parámetros de acción
description: Obtenga información sobre cómo definir los parámetros de acción
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Definición de los parámetros de acción {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

En la sección **[!UICONTROL Action parameters]** , pegue un ejemplo de la carga útil JSON para enviarla al servicio externo.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Los nombres de campo de la carga útil no pueden contener &quot;.&quot; carácter. No pueden empezar con un carácter &quot;$&quot;.

Puede definir el tipo de parámetro (p. ej.: string, integer, etc.).

También tendrá la opción de especificar si un parámetro es una constante o una variable:

* Constante significa que el valor del parámetro se define en el panel de configuración de acciones mediante un perfil técnico. El valor siempre será el mismo en todos los recorridos. No variará y el especialista en marketing no lo verá al utilizar la acción personalizada en el recorrido. Podría ser, por ejemplo, un ID que el sistema de terceros espera. En ese caso, el campo a la derecha de la constante o variable de alternancia es el valor pasado.
* Variable significa que el valor del parámetro variará. El especialista en marketing que utilice esta acción personalizada en un recorrido podrá pasar el valor que desee o especificar dónde recuperar el valor para este parámetro (por ejemplo, desde el evento, desde Adobe Experience Platform, etc.). En ese caso, el campo a la derecha de la constante o variable de alternancia es la etiqueta que el especialista en marketing verá en el recorrido para asignar un nombre a este parámetro.

![](../assets/customactionpayloadmessage2.png)
