---
product: adobe campaign
title: Definición de la clave del evento
description: Obtenga información sobre cómo definir la clave de evento
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# Definición de la clave del evento {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


La clave es el campo o la combinación de campos que forma parte de los datos de carga útil de evento y que permitirá al sistema identificar a la persona asociada al evento. La clave puede ser, por ejemplo, el Experience Cloud ID, un ID de CRM o una dirección de correo electrónico.

Si planea aprovechar los datos almacenados en la base de datos Perfil del cliente en tiempo real, debe seleccionar, como clave de evento, la información que definió como identidad de perfil en el [servicio Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es).

Permitirá al sistema realizar la reconciliación entre el evento y el perfil del individuo. Si selecciona un esquema que tiene una identidad principal, los campos **[!UICONTROL Key]** y **[!UICONTROL Namespace]** se rellenan previamente. Si no se ha definido ninguna identidad, se selecciona _identityMap > id_ como clave principal. A continuación, debe seleccionar un área de nombres y la clave se rellenará previamente (debajo del campo **[!UICONTROL Namespace]**) mediante _identityMap > id_.

Al seleccionar campos, los campos de identidad principales se etiquetan.

![](../assets/primary-identity.png)

Si necesita utilizar una clave diferente, como un ID de CRM o una dirección de correo electrónico, debe agregarla manualmente:

1. Haga clic dentro del campo **[!UICONTROL Key]** o en el icono de lápiz.

   ![](../assets/journey16.png)

1. Seleccione el campo elegido como clave en la lista de campos de carga útil. También puede cambiar al editor de expresiones avanzadas para crear claves más complejas (por ejemplo, una concatenación de dos campos de los eventos). Consulte a continuación, en esta sección.

   ![](../assets/journey20.png)

Cuando se recibe el evento, el valor de la clave permite al sistema identificar a la persona asociada al evento. Asociada a un área de nombres (vea [esta página](../event/selecting-the-namespace.md)), la clave se puede usar para realizar consultas en Adobe Experience Platform. Ver [esta página](../building-journeys/about-orchestration-activities.md).
La clave también se utiliza para comprobar que una persona está en un recorrido. De hecho, una persona no puede estar en dos lugares diferentes en el mismo recorrido. Como resultado, el sistema no permite que la misma clave, por ejemplo la clave CRMID=3224, esté en diferentes lugares del mismo recorrido.

También tiene acceso a las funciones de expresiones avanzadas (**[!UICONTROL Advanced mode]**) si desea realizar manipulaciones adicionales. Estas funciones permiten manipular los valores utilizados para llevar a cabo consultas específicas, como cambiar de formato, o realizar concatenaciones de campos, teniendo en cuenta solo una parte de un campo (por ejemplo, los 10 primeros caracteres). Consulte [esta página](../expression/expressionadvanced.md).
