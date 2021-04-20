---
product: adobe campaign
solution: Journey Orchestration
title: Añadir una condición
description: Aprenda a añadir una condición
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 4%

---



# Añadir una condición {#concept_rbg_gqt_52b}

Para los eventos generados por el sistema, puede definir una condición de evento que permita al sistema filtrar el procesamiento de los eventos. Si la condición es verdadera, se procesa el evento. Si la condición no es verdadera, se ignora el evento.

La condición de los eventos solo se puede basar en los datos pasados en la carga útil del evento. Un especialista en marketing no puede cambiar la condición definida en el nivel de evento en el lienzo. El propósito es endurecer esta condición cuando se utiliza este evento. Por ejemplo: si nunca desea que los especialistas en marketing utilicen eventos de abandono del carro de compras si el valor del carro de compras es demasiado pequeño, puede crear una condición en el campo de evento &quot;valor del carro de compras&quot; e imponer un valor superior a 100 dólares.

Puede utilizar el editor de expresiones simple o el editor de expresiones avanzadas para configurar las condiciones en los eventos. Consulte [esta página](../expression/expressionadvanced.md).

Por ejemplo, puede definir una condición para procesar solo los eventos de un tipo de evento específico e ignorar los demás tipos. O si el evento es un abandono del carro de compras y la carga útil incluye el campo valor del carro de compras, puede definir una condición de evento para procesar los eventos solo si el valor del carro de compras es bueno a más de 100 dólares.

![](../assets/journey78.png)
