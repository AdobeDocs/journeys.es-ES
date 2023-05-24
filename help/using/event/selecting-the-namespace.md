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
source-wordcount: '200'
ht-degree: 12%

---

# Selección del área de nombres {#concept_ckb_3qt_52b}

El área de nombres permite definir el tipo de clave utilizada para identificar a la persona asociada al evento. Su configuración es opcional. Es necesario si desea recuperar, en sus recorridos, información adicional proveniente de [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es). La definición del área de nombres no es necesaria si solo utiliza datos procedentes de un sistema de terceros a través de una fuente de datos personalizada.

Puede utilizar uno de los predefinidos o crear uno nuevo mediante el servicio Área de nombres de identidad. Consulte [esta página](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es).

Si selecciona un esquema que tiene una identidad principal, la variable **[!UICONTROL Key]** y **[!UICONTROL Namespace]** los campos están rellenados previamente. Si no se ha definido ninguna identidad, se selecciona _identityMap > id_ como clave principal. A continuación, debe seleccionar un área de nombres y la clave se rellenará previamente (debajo de la etiqueta **[!UICONTROL Namespace]** field) utilizando _identityMap > id_.

Al seleccionar campos, los campos de identidad principales se etiquetan.

![](../assets/primary-identity.png)


Seleccione un área de nombres de la lista desplegable.

![](../assets/journey17.png)

Solo se permite un área de nombres por recorrido. Si utiliza varios eventos en el mismo recorrido, deben utilizar el mismo área de nombres. Consulte [esta página](../building-journeys/journey.md).
