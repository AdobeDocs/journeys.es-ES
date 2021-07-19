---
product: adobe campaign
title: Selección del área de nombres
description: Obtenga información sobre cómo seleccionar el área de nombres
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 12%

---

# Selección del área de nombres {#concept_ckb_3qt_52b}

El espacio de nombres permite definir el tipo de clave utilizada para identificar a la persona asociada al evento. Su configuración es opcional. Es necesario si desea recuperar, en sus recorridos, información adicional proveniente del [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es). La definición del área de nombres no es necesaria si solo utiliza datos procedentes de un sistema de terceros a través de una fuente de datos personalizada.

Puede utilizar uno de los predefinidos o crear uno nuevo mediante el servicio Área de nombres de identidad . Consulte [esta página](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es).

Si selecciona un esquema que tiene una identidad principal, los campos **[!UICONTROL Key]** y **[!UICONTROL Namespace]** se rellenan previamente. Si no hay ninguna identidad definida, seleccione _identityMap > id_ como clave principal. A continuación, debe seleccionar un área de nombres y la clave se rellenará previamente (debajo del campo **[!UICONTROL Namespace]**) mediante _identityMap > id_.

Al seleccionar campos, los campos de identidad principales se etiquetan.

![](../assets/primary-identity.png)


Seleccione un área de nombres en la lista desplegable.

![](../assets/journey17.png)

Solo se permite un espacio de nombres por recorrido. Si utiliza varios eventos en el mismo recorrido, deben utilizar el mismo espacio de nombres. Consulte [esta página](../building-journeys/journey.md).
