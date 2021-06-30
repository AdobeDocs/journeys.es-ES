---
product: adobe campaign
title: Cambio de las propiedades
description: Obtenga información sobre cómo cambiar propiedades
feature: Recorridos
role: Business Practitioner
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 58891c1bddd8fb9b0ae247d54be5cf1d7c40b9a8
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Cambio de las propiedades {#concept_prq_wqt_52b}

Haga clic en el icono de lápiz, en la parte superior derecha para acceder a las propiedades del recorrido.

Puede cambiar el nombre del recorrido, añadir una descripción, permitir la reentrada, elegir las fechas de inicio y finalización y definir una **[!UICONTROL Timeout and error]** duración si es administrador.

Para los recorridos en directo, esta pantalla muestra la fecha de publicación y el nombre del usuario que publicó el recorrido.

El **Copy technical details** permite copiar información técnica sobre el recorrido que el equipo de asistencia puede utilizar para solucionar problemas. Se copia la siguiente información: UID de JourneyVersion, OrgID, orgName, sandboxName, lastDedeployBy, lastDedeployAt.

![](../assets/journey32.png)

## Entrada{#entrance}

De forma predeterminada, los nuevos recorridos permiten volver a entrar. Puede desmarcar la opción de recorridos de &quot;una toma&quot;, por ejemplo, si desea ofrecer un regalo único cuando una persona entra en una tienda. En ese caso, no desea que el cliente pueda volver a entrar en el recorrido y recibir la oferta de nuevo.

Cuando un recorrido &quot;termina&quot;, tendrá el estado **[!UICONTROL Closed (no entrance)]**. El recorrido dejará de permitir la entrada al recorrido de nuevos individuos. Las personas que ya están en el recorrido terminarán normalmente el recorrido.

Después del tiempo de espera global predeterminado de 30 días, el recorrido cambiará al estado **Finalizado**. Consulte esta [sección](#global_timeout).

## Tiempo de espera y error en actividades de recorrido {#timeout_and_error}

Al editar una acción o actividad de condición, puede definir una ruta alternativa en caso de error o de tiempo de espera. Si el procesamiento de la actividad que interroga a un sistema de terceros supera la duración de tiempo de espera definida en las propiedades del recorrido (campo **[!UICONTROL Timeout and  error]**), se elegirá la segunda ruta para realizar una posible acción de reserva.

Los valores autorizados están entre 1 y 30 segundos.

Se recomienda definir un valor **[!UICONTROL Timeout and error]** muy corto si el recorrido distingue entre tiempo (por ejemplo: reaccionar a la ubicación en tiempo real de una persona) porque no puede retrasar la acción durante más de unos segundos. Si el recorrido es menos sensible al tiempo, puede utilizar un valor más largo para dar más tiempo al sistema llamado para enviar una respuesta válida.

[!DNL Journey Orchestration] también utiliza un tiempo de espera global. Consulte la [siguiente sección](#global_timeout).

## Tiempo de espera de recorrido global {#global_timeout}

Además del [timeout](#timeout_and_error) utilizado en las actividades de recorrido, también existe un tiempo de espera de recorrido global que no se muestra en la interfaz y que no se puede cambiar. Este tiempo de espera detendrá el progreso de las personas en el recorrido 30 días después de su entrada. Esto significa que el recorrido de una persona no puede durar más de 30 días. Después del tiempo de espera de 30 días, se eliminan los datos del individuo. Las personas que sigan fluyendo en el recorrido al final del tiempo de espera se detendrán y se tendrán en cuenta como errores en los informes.

>[!NOTE]
>
>[!DNL Journey Orchestration] no reacciona directamente a las solicitudes de exclusión, acceso o eliminación de privacidad. Sin embargo, el tiempo de espera global garantiza que las personas nunca permanezcan más de 30 días en ningún recorrido.

Debido al tiempo de espera de recorrido de 30 días, cuando no se permite la reentrada del recorrido, no podemos asegurarnos de que el bloqueo de reentrada funcione más de 30 días. De hecho, como eliminamos toda la información sobre las personas que entraron en el recorrido 30 días después de su entrada, no podemos conocer a la persona ingresada anteriormente, hace más de 30 días.

## Zona horaria y zona horaria del perfil {#timezone}

La zona horaria se define en el nivel de recorrido.

Puede introducir una zona horaria fija o utilizar perfiles de Adobe Experience Platform para definir la zona horaria del recorrido.

Para obtener más información sobre la administración de huso horario, consulte [esta página](../building-journeys/timezone-management.md).
