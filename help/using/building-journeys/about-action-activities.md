---
product: adobe campaign
title: Acerca de las actividades de acción
description: Más información sobre las actividades de acción
feature: Journeys
role: User
level: Intermediate
exl-id: 5436602f-af7a-41db-8b10-d3d28a6d0cd0
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 22%

---

# Acerca de las actividades de acción {#concept_hbj_hrt_52b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._



En la paleta, en el lado izquierdo de la pantalla, debajo de **[!UICONTROL Events]** y **[!UICONTROL Orchestration]**, se encuentra la categoría **[!UICONTROL Actions]**.

![](../assets/journey58.png)

Estas actividades representan los diferentes canales de comunicación disponibles. Puede combinarlas para crear un escenario de canales cruzados.

Si tiene Adobe Campaign Standard, están disponibles las siguientes actividades de acción integradas: **[!UICONTROL Email]**, **[!UICONTROL Push]** y **[!UICONTROL SMS]**. Consulte [esta página](../building-journeys/using-adobe-campaign-actions.md).

Si ha configurado acciones personalizadas, también aparecerán aquí (vea [esta página](../building-journeys/using-custom-actions.md)).

Cuando suelte una actividad de acción en el lienzo, puede definir un(a) **[!UICONTROL Label]**. Esto le permite agregar un sufijo al nombre de la acción que aparecerá bajo su actividad en el lienzo. Esto resulta útil si utiliza la misma acción varias veces en el recorrido y desea identificarlas más fácilmente. Los informes también serán más fáciles de leer. También puede agregar un(a) **[!UICONTROL Description]** opcional.

![](../assets/journey59bis.png)

Cuando se produce un error en una acción o condición, se detiene el recorrido de un individuo. La única manera para continuar es marcar la casilla **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta sección](../building-journeys/using-the-journey-designer.md#paths).
