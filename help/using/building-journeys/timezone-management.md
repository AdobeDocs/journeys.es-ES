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
source-git-commit: f4f41428b19f611da15b20a1788b240fadfd49fa

---



# Administración de husos horarios {#timezone_management}

Puede definir una zona horaria en las [propiedades](../building-journeys/changing-properties.md) del viaje.

Para acceder a Propiedades, haga clic en el icono del lápiz en la parte superior derecha de la pantalla.

Esta zona horaria se utilizará para cada actividad del viaje que contenga un elemento de tiempo como:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Puede seleccionar una zona horaria o elegir utilizar la zona horaria definida en el perfil de usuario.

## Definición de una zona horaria fija {#fixed-timezone}

El huso horario también se puede corregir. Borre el huso horario predefinido y elija uno en la lista desplegable. Si utiliza un huso horario fijo, será el mismo para todas las personas que entren en el viaje.

Para ello, en **[!UICONTROL Properties]**, seleccione un huso horario.

![](../assets/journey73.png)

## Uso de perfiles para definir la zona horaria del viaje {#timezone-from-profiles}

Si el evento de entrada del viaje tiene un espacio de nombres, lo que significa que el viaje puede alcanzar el servicio Perfil del cliente en tiempo real de la plataforma de datos, el huso horario se define previamente con el especificado en el perfil del individuo que fluye en el viaje.

Si se define una zona horaria en el perfil de la plataforma de experiencias, se puede recuperar en el viaje.

Si el perfil del individuo no contiene una zona horaria, la zona horaria recuperada será la definida en el campo de zona horaria.

Para hacerlo, en **[!UICONTROL Properties]**, verifique **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Uso de zonas horarias en expresiones {#timezone-in-expressions}

Los husos horarios se utilizan para generar expresiones con el editor de expresiones avanzado. En este caso, utilizará el editor de expresiones para seleccionar dónde desea que el sistema obtenga esta información. Consulte [](../expression/expressionadvanced.md).

Las fechas de inicio y finalización de un viaje no se pueden vincular a un huso horario específico. Se asocian automáticamente al huso horario de la instancia.
