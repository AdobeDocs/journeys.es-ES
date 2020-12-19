---
product: adobe campaign
solution: Journey Orchestration
title: Cambio de las propiedades
description: Obtenga información sobre cómo cambiar las propiedades
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---



# Cambio de las propiedades {#concept_prq_wqt_52b}

Haga clic en el icono del lápiz, en la parte superior derecha para acceder a las propiedades del viaje.

Puede cambiar el nombre del viaje, agregar una descripción, permitir la reentrada, elegir las fechas de inicio y finalización y definir una **[!UICONTROL Timeout and error]** duración si es administrador.

![](../assets/journey32.png)

## Entrada{#entrance}

De forma predeterminada, los viajes nuevos permiten la reentrada. Puede desmarcar la opción de viajes de &quot;un tiro&quot;, por ejemplo si desea oferta de un regalo único cuando una persona entra en una tienda. En ese caso, no desea que el cliente pueda volver a entrar en el viaje y recibir la oferta de nuevo.

Cuando un viaje &quot;termina&quot;, tendrá el estado **[!UICONTROL Closed (no entrance)]**. El viaje dejará de permitir que nuevos individuos entren al viaje. Las personas que ya están en el viaje terminarán normalmente el viaje.

## Tiempo de espera y error en actividades de viaje {#timeout_and_error}

Al editar una acción o actividad de condición, puede definir una ruta alternativa en caso de error o de tiempo de espera. Si el procesamiento de la actividad que realiza el interrogatorio en un sistema de terceros supera la duración de tiempo de espera definida en el campo de propiedades del viaje (**[!UICONTROL Timeout and  error]**), se elegirá la segunda ruta para realizar una posible acción de reserva.

Los valores autorizados están entre 1 y 30 segundos.

Le recomendamos que defina un valor muy corto **[!UICONTROL Timeout and error]** si su viaje distingue entre tiempo (por ejemplo: reaccionar a la ubicación en tiempo real de una persona) porque no puede retrasar la acción durante más de unos segundos. Si su viaje es menos sensible al tiempo, puede utilizar un valor más largo para dar más tiempo al sistema llamado para enviar una respuesta válida.

[!DNL Journey Orchestration] también utiliza un tiempo de espera global. Consulte la [siguiente sección](#global_timeout).

## Tiempo de espera de viaje global {#global_timeout}

Además del [tiempo de espera](#timeout_and_error) utilizado en las actividades de viaje, también existe un tiempo de espera de viaje global que no se muestra en la interfaz y que no se puede cambiar. Este tiempo de espera detendrá el progreso de los individuos en el viaje 30 días después de su entrada. Esto significa que el viaje de una persona no puede durar más de 30 días. Después del período de tiempo de espera de 30 días, se eliminan los datos del individuo. Las personas que sigan viajando al final del tiempo de espera se detendrán y se tendrán en cuenta como errores en el sistema de informes.

>[!NOTE]
>
>[!DNL Journey Orchestration] no reacciona directamente a las solicitudes de exclusión, acceso o eliminación de privacidad. Sin embargo, el tiempo de espera global garantiza que los individuos nunca permanezcan más de 30 días en ningún viaje.

Debido al tiempo de espera de viaje de 30 días, cuando no se permite la reentrada del viaje, no podemos asegurarnos de que el bloqueo de reentrada funcione más de 30 días. De hecho, al retirar toda la información sobre las personas que entraron 30 días después de su entrada, no podemos conocer a la persona que entró anteriormente, hace más de 30 días.

## Zona horaria y zona horaria del perfil {#timezone}

La zona horaria se define en el nivel de viaje.

Puede introducir una zona horaria fija o utilizar perfiles de Adobe Experience Platform para definir la zona horaria del viaje.

Para obtener más información sobre la administración de huso horario, consulte [esta página](../building-journeys/timezone-management.md).
