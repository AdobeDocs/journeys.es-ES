---
title: Limitaciones de acciones personalizadas
description: Más información sobre las limitaciones de las acciones personalizadas
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
source-git-commit: 2a55139697347ade80959f60bf52bfde39e43eb9
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 5%

---


# Limitaciones de acciones personalizadas {#concept_lh2_df1_2gb}

Estas son algunas limitaciones con respecto al uso de acciones personalizadas:

* No existe el almacenamiento en búfer/suavizado del volumen de envío.
* En caso de error se realizan dos reintentos de forma sistemática. No se puede ajustar el número de reintentos según el mensaje de error recibido.
* El **[!UICONTROL Reaction]** evento integrado le permite reaccionar a las acciones integradas (consulte [](../building-journeys/reaction-events.md)). Si desea reaccionar a un mensaje enviado mediante una acción personalizada, debe configurar un evento dedicado.
* La URL de acción personalizada no admite parámetros dinámicos.
* Solo se admiten los métodos de llamada POST y PUT.
* El nombre del parámetro de consulta o del encabezado no debe tener inicio con &quot;.&quot; o &quot;$&quot;.
* No se permiten direcciones IP.
* Direcciones internas de Adobe (.adobe.) no se permiten.
