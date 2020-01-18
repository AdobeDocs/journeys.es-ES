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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Administración de husos horarios {#timezone_management}

La definición de zona horaria está disponible en las siguientes actividades:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Si el evento de entrada del viaje tiene un espacio de nombres, lo que significa que el viaje puede alcanzar el servicio Perfil del cliente en tiempo real de la plataforma de datos, el huso horario se define previamente con el especificado en el perfil del individuo que fluye en el viaje. Si el perfil del individuo no contiene una zona horaria, se utiliza la zona horaria de la instancia. Puede ponerse en contacto con el administrador para conocer el huso horario de la instancia.

![](../assets/journey73.png)

El huso horario también se puede corregir. Borre el huso horario predefinido y elija uno en la lista desplegable. Si utiliza un huso horario fijo, será el mismo para todas las personas que entren en el viaje.

![](../assets/journey72.png)

Por último, el huso horario puede ser dinámico para cada persona que introduzca el paso. En este caso, utilizará el editor de expresiones para seleccionar dónde desea que el sistema obtenga esta información (puede proceder de un evento o de un origen de datos). Consulte [](../expression/expressionadvanced.md).


Las fechas de inicio y finalización de un viaje no se pueden vincular a un huso horario específico. Se asocian automáticamente al huso horario de la instancia.
