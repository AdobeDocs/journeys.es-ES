---
title: Definición de la clave del evento
description: Aprenda a definir la clave de evento
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Definición de la clave del evento {#concept_ond_hqt_52b}

La clave es el campo o la combinación de campos que forma parte de los datos de carga útil de evento y que permitirá al sistema identificar a la persona asociada al evento. La clave puede ser, por ejemplo, el ID de Experience Cloud, un ID de CRM o una dirección de correo electrónico.

Si planea aprovechar los datos almacenados en la base de datos de Perfil del cliente en tiempo real, debe seleccionar, como clave de evento, la información que definió como la identidad de un perfil en el servicio [de Perfil del cliente en tiempo](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)real.

Permitirá al sistema llevar a cabo la conciliación entre el evento y el perfil del individuo. Si selecciona un esquema que tiene una identidad principal, los campos **[!UICONTROL Key]** y **[!UICONTROL Namespace]** se rellenan previamente. Si no hay ninguna identidad definida, seleccionamos _identityMap > id_ como clave principal. A continuación, debe seleccionar una Área de nombres y la clave se rellenará previamente (debajo del **[!UICONTROL Namespace]** campo) mediante _identityMap > id_.

Al seleccionar campos, los campos de identidad principales se etiquetan.

![](../assets/primary-identity.png)

Si necesita utilizar una clave diferente, como un ID de CRM o una dirección de correo electrónico, debe agregarla manualmente:

1. Haga clic dentro del **[!UICONTROL Key]** campo o en el icono del lápiz.

   ![](../assets/journey16.png)

1. Seleccione el campo elegido como clave en la lista de campos de carga útil. También puede cambiar al editor de expresiones avanzado para crear claves más complejas (por ejemplo, una concatenación de dos campos de los eventos). Véase más abajo, en esta sección.

   ![](../assets/journey20.png)

Cuando se recibe el evento, el valor de la clave permitirá al sistema identificar a la persona asociada al evento. Asociada a una Área de nombres (consulte [](../event/selecting-the-namespace.md)), la clave se puede utilizar para realizar consultas en la plataforma de Adobe Experience. Consulte [](../building-journeys/about-orchestration-activities.md).
La llave también se utiliza para comprobar que una persona está en un viaje. De hecho, una persona no puede estar en dos lugares diferentes en el mismo viaje. Como resultado, el sistema no permite que la misma clave, por ejemplo la clave CRMID=3224, esté en diferentes lugares en el mismo viaje.

También tiene acceso a las funciones de expresión avanzadas (**[!UICONTROL Advanced mode]**) si desea realizar manipulaciones adicionales. Estas funciones le permiten manipular los valores utilizados para llevar a cabo consultas específicas, como cambiar los formatos, realizar concatenaciones de campo, teniendo en cuenta sólo una parte de un campo (por ejemplo, los 10 primeros caracteres). Consulte [](../expression/expressionadvanced.md).
