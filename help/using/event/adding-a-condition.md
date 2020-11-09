---
title: Añadir una condición
description: Aprenda a agregar una condición
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---



# Añadir una condición {#concept_rbg_gqt_52b}

La condición de evento permite al sistema filtrar el procesamiento de eventos. Si la condición es verdadera, se procesa el evento. Si la condición no es verdadera, se ignora el evento.

La condición de los eventos solo puede basarse en los datos pasados en la carga útil de evento. Un especialista en marketing no puede cambiar la condición definida en el nivel de evento en el lienzo. El propósito es endurecer esta condición cuando se utiliza este evento. Por ejemplo: si nunca desea que los especialistas en marketing utilicen eventos de abandono del carro de compras si el valor del carro de compras es demasiado pequeño, puede crear una condición en el campo de evento &quot;valor del carro de compras&quot; e imponer un valor superior a 100 dólares.

Puede utilizar el editor de expresiones simple o el editor de expresiones avanzado para configurar las condiciones en los eventos. Consulte [esta página](../expression/expressionadvanced.md).

Por ejemplo, puede definir una condición para procesar solo los eventos de un tipo de evento específico e ignorar los demás tipos. O bien, si el evento es un abandono del carro de compras y la carga útil incluye el campo de valor del carro de compras, puede definir una condición de evento para procesar los eventos únicamente si el valor del carro de compras es bueno a más de 100 dólares.

![](../assets/journey78.png)
