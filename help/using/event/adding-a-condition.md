---
product: adobe campaign
title: Añadir una condición
description: Aprenda a añadir una condición
feature: Journeys
role: User
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 4%

---

# Añadir una condición {#concept_rbg_gqt_52b}

Para los eventos generados por el sistema, puede definir una condición de evento que permita al sistema filtrar el procesamiento de los eventos. Si la condición es verdadera, se procesa el evento. Si la condición no es verdadera, se ignora el evento.

La condición de los eventos solo se puede basar en los datos pasados en la carga útil del evento. Un especialista en marketing no puede cambiar la condición definida en el nivel de evento en el lienzo. El propósito es endurecer esta condición cuando se utiliza este evento. Por ejemplo: si nunca desea que los especialistas en marketing utilicen eventos de abandono del carro de compras si el valor del carro de compras es demasiado pequeño, puede crear una condición en el campo de evento &quot;valor del carro de compras&quot; e imponer un valor superior a 100 dólares.

Puede utilizar el editor de expresiones simple o el editor de expresiones avanzadas para configurar las condiciones en los eventos. Consulte [esta página](../expression/expressionadvanced.md).

Por ejemplo, puede definir una condición para procesar solo los eventos de un tipo de evento específico e ignorar los demás tipos. O si el evento es un abandono del carro de compras y la carga útil incluye el campo valor del carro de compras, puede definir una condición de evento para procesar los eventos solo si el valor del carro de compras es bueno a más de 100 dólares.

![](../assets/journey78.png)
