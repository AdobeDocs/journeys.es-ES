---
title: Selección del espacio de nombres
description: Aprenda a seleccionar el espacio de nombres
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

---


# Selección del espacio de nombres {#concept_ckb_3qt_52b}

El espacio de nombres permite definir el tipo de clave utilizada para identificar a la persona asociada al evento. Su configuración es opcional. Se requiere si desea recuperar, en sus viajes, información adicional proveniente del Perfil [del cliente en tiempo](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)real. La definición de espacio de nombres no es necesaria si solo se utilizan datos procedentes de un sistema de terceros a través de un origen de datos personalizado.

Puede utilizar uno de los predefinidos o crear uno nuevo con el servicio Espacio de nombres de identidad. Consulte [esta página](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md).

Si selecciona un esquema que tiene una identidad principal, los campos **[!UICONTROL Key]**y**[!UICONTROL Namespace]** se rellenan previamente. Si no hay ninguna identidad definida, seleccionamos _identityMap > id_ como clave principal. A continuación, debe seleccionar un espacio de nombres y la clave se rellenará previamente (debajo del **[!UICONTROL Namespace]**campo) mediante _identityMap > id_.

Seleccione un espacio de nombres en la lista desplegable.

![](../assets/journey17.png)

Solo se permite un espacio de nombres por viaje. Si utiliza varios eventos en el mismo viaje, deben utilizar el mismo espacio de nombres. Consulte [](../building-journeys/journey.md).
