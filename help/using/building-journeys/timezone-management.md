---
product: adobe campaign
title: Administración de husos horarios
description: Obtenga información sobre la administración de husos horarios
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Administración de husos horarios {#timezone_management}

Puede definir una zona horaria en la variable [propiedades](../building-journeys/changing-properties.md) de su recorrido.

Para acceder a Propiedades, haga clic en el icono de lápiz en la parte superior derecha de la pantalla.

Esta zona horaria se utilizará para todas las actividades del recorrido que contengan un elemento horario como:

* [Condición horaria](../building-journeys/condition-activity.md#time_condition)
* [Condición de fecha](../building-journeys/condition-activity.md#date_condition)
* [Espera personalizada](../building-journeys/wait-activity.md#custom)
* [Fecha de espera fija](../building-journeys/wait-activity.md#fixed_date)

Puede seleccionar una zona horaria o elegir usar la zona horaria definida en el perfil del usuario.

>[!NOTE]
>
>La zona horaria del perfil funciona con la variable **timeZone** campo existente en la variable **Detalles de preferencia** grupo de campos.

## Definición de una zona horaria fija {#fixed-timezone}

La zona horaria también se puede corregir. Borre la zona horaria predefinida y elija una de la lista desplegable. Si utiliza una zona horaria fija, será la misma para todas las personas que entren en el recorrido.

Para ello, en **[!UICONTROL Properties]**, seleccione una zona horaria.

![](../assets/journey72.png)

## Uso de perfiles para definir la zona horaria del recorrido {#timezone-from-profiles}

Si el evento de entrada del recorrido tiene un área de nombres, lo que significa que el recorrido puede llegar al servicio Perfil del cliente en tiempo real de Adobe Experience Platform, la zona horaria se predefine con la especificada en el perfil del individuo que fluye en el recorrido.

Si se define una zona horaria en el perfil de Adobe Experience Platform, se puede recuperar en el recorrido .

Si el perfil de la persona no contiene una zona horaria, la zona horaria recuperada será la definida en el campo de zona horaria.

Para ello, en **[!UICONTROL Properties]**, compruebe **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey73.png)

## Uso de zonas horarias en expresiones {#timezone-in-expressions}

Las fechas de inicio y finalización de un recorrido no se pueden vincular a un huso horario específico. Se asocian automáticamente al huso horario de la instancia.
