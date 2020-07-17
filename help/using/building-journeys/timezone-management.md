---
title: Administración de husos horarios
description: Obtenga información sobre la administración de husos horarios
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 2%

---



# Administración de husos horarios {#timezone_management}

Puede definir una zona horaria en las [propiedades](../building-journeys/changing-properties.md) del viaje.

Para acceder a Propiedades, haga clic en el icono del lápiz en la parte superior derecha de la pantalla.

Este huso horario se utilizará para cada actividad del viaje que contenga un elemento de tiempo como:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Puede seleccionar una zona horaria o elegir utilizar la zona horaria definida en el perfil del usuario.

## Definición de una zona horaria fija {#fixed-timezone}

El huso horario también se puede corregir. Borre el huso horario predefinido y elija uno en la lista desplegable. Si utiliza un huso horario fijo, será el mismo para todas las personas que entren en el viaje.

Para ello, en **[!UICONTROL Properties]**, seleccione un huso horario.

![](../assets/journey73.png)

## Uso de perfiles para definir la zona horaria del viaje {#timezone-from-profiles}

Si el evento de entrada del viaje tiene una Área de nombres, lo que significa que el viaje puede llegar al servicio de Perfil del cliente en tiempo real del Adobe Experience Platform, el huso horario se define previamente con el especificado en el perfil del viajero.

Si se define una zona horaria en el perfil de Adobe Experience Platform, se puede recuperar en el viaje.

Si el perfil del individuo no contiene una zona horaria, la zona horaria recuperada será la definida en el campo de zona horaria.

Para hacerlo, en **[!UICONTROL Properties]**, verifique **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Uso de husos horarios en expresiones {#timezone-in-expressions}

Las fechas de inicio y finalización de un viaje no pueden vincularse a un huso horario específico. Se asocian automáticamente al huso horario de la instancia.
