---
title: Selección del área de nombres
description: Aprenda a seleccionar la Área de nombres
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---


# Selección del área de nombres {#concept_ckb_3qt_52b}

La Área de nombres permite definir el tipo de clave utilizada para identificar a la persona asociada al evento. Su configuración es opcional. Se requiere si desea recuperar, en sus viajes, información adicional procedente del Perfil [del cliente en tiempo](https://docs.adobe.com/content/help/es-ES/experience-platform/profile/home.html)real. La definición de Área de nombres no es necesaria si solo se utilizan datos procedentes de un sistema de terceros a través de un origen de datos personalizado.

Puede utilizar uno de los predefinidos o crear uno nuevo mediante el servicio de Área de nombres de identidad. Consulte [esta página](https://docs.adobe.com/content/help/es-ES/experience-platform/identity/home.html).

Si selecciona un esquema que tiene una identidad principal, los campos **[!UICONTROL Key]** y **[!UICONTROL Namespace]** se rellenan previamente. Si no hay ninguna identidad definida, seleccionamos _identityMap > id_ como clave principal. A continuación, debe seleccionar una Área de nombres y la clave se rellenará previamente (debajo del **[!UICONTROL Namespace]** campo) mediante _identityMap > id_.

Al seleccionar campos, los campos de identidad principales se etiquetan.

![](../assets/primary-identity.png)


Seleccione una Área de nombres en la lista desplegable.

![](../assets/journey17.png)

Sólo se permite una Área de nombres por viaje. Si utiliza varios eventos en el mismo viaje, deben utilizar la misma Área de nombres. Consulte [](../building-journeys/journey.md).
