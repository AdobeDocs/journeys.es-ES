---
product: adobe campaign
title: Definición de los parámetros del mensaje
description: Obtenga información sobre cómo definir los parámetros de acción
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 21%
---
# Definición de los parámetros del mensaje {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


![](../assets/messageparameterssection.png)

En la sección **[!UICONTROL Action parameters]**, pegue un ejemplo de la carga útil JSON para enviarla al servicio externo.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Los nombres de campo en la carga no pueden contener un &quot;&quot;. carácter. No pueden comenzar con el carácter &quot;$&quot;.

Podrá definir el tipo de parámetro (por ejemplo, cadena, entero, etc.).

También puede elegir entre especificar si un parámetro es una constante o una variable:

* Constante significa que el valor del parámetro se define en el panel de configuración de acciones por una persona técnica. El valor siempre será el mismo en todos los recorridos. No variará y el experto en marketing no lo verá al utilizar la acción personalizada en el recorrido. Podría ser, por ejemplo, un ID que espere el sistema de terceros. En ese caso, el campo a la derecha de la constante/variable de alternancia es el valor pasado.
* Variable significa que el valor del parámetro variará. El experto en marketing que utilice esta acción personalizada en un recorrido podrá transferir libremente el valor que desee o especificar dónde recuperar el valor de este parámetro (por ejemplo, desde el evento, desde Adobe Experience Platform, etc.). En ese caso, el campo a la derecha de la constante/variable de alternancia es la etiqueta que el experto en marketing verá en el recorrido para asignar un nombre a este parámetro.

![](../assets/customactionpayloadmessage2.png)
