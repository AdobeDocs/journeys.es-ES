---
product: adobe campaign
title: Cambio de las propiedades
description: Obtenga información sobre cómo cambiar propiedades
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 2%

---

# Cambio de las propiedades {#concept_prq_wqt_52b}

Haga clic en el icono de lápiz, en la parte superior derecha para acceder a las propiedades del recorrido.

Puede cambiar el nombre del recorrido, agregar una descripción, permitir la reentrada, elegir las fechas de inicio y finalización y definir una duración de **[!UICONTROL Timeout and error]** si es el administrador.

En el caso de los recorridos activos, esta pantalla muestra la fecha de publicación y el nombre del usuario que publicó el recorrido.

**Copiar detalles técnicos** le permite copiar información técnica sobre el recorrido que el equipo de soporte técnico puede usar para solucionar problemas. Se copia la siguiente información: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## Entrada{#entrance}

De forma predeterminada, los nuevos recorridos permiten la reentrada. Puede desmarcar la opción para recorridos de &quot;una sola vez&quot;, por ejemplo, si desea ofrecer un regalo de una sola vez cuando una persona entra en una tienda. En ese caso, no desea que el cliente pueda volver a introducir el recorrido y recibir la oferta de nuevo.

Cuando un recorrido &quot;termina&quot;, tendrá el estado **[!UICONTROL Closed (no entrance)]**. El recorrido dejará de permitir que nuevas personas entren al recorrido. Las personas que ya están en el recorrido terminarán el recorrido normalmente.

Después del tiempo de espera global predeterminado de 30 días, el recorrido cambiará al estado **Finalizado**. Consulte esta [sección](#global_timeout).

## Tiempo de espera y error en actividades de recorrido {#timeout_and_error}

Al editar una actividad de acción o condición, puede definir una ruta alternativa en caso de error o tiempo de espera. Si el procesamiento de la actividad que busca un sistema de terceros supera el tiempo de espera definido en las propiedades del recorrido (campo **[!UICONTROL Timeout and  error]**), se elegirá la segunda ruta para realizar una posible acción de reserva.

Los valores autorizados están entre 1 y 30 segundos.

Le recomendamos que defina un valor **[!UICONTROL Timeout and error]** muy corto si el recorrido distingue entre tiempo y minúsculas (por ejemplo: reacción a la ubicación en tiempo real de una persona) porque no puede retrasar la acción más de unos segundos. Si el recorrido distingue menos del tiempo, puede utilizar un valor más largo para dar más tiempo al sistema llamado para enviar una respuesta válida.

[!DNL Journey Orchestration] también usa un tiempo de espera global. Ver [siguiente sección](#global_timeout).

## Tiempo de espera de recorrido global {#global_timeout}

Además del tiempo de espera [timeout](#timeout_and_error) utilizado en las actividades de recorrido, también hay un tiempo de espera de recorrido global que no se muestra en la interfaz y no se puede cambiar. Este tiempo de espera detiene el progreso de las personas en el recorrido 30 días después de su entrada. Esto significa que el recorrido de una persona no puede durar más de 30 días. Después del periodo de espera de 30 días, se eliminan los datos del individuo. Las personas que sigan fluyendo en el recorrido al final del periodo de tiempo de espera se detendrán y se tendrán en cuenta como errores en la creación de informes.

>[!NOTE]
>
>[!DNL Journey Orchestration] no reacciona directamente a las solicitudes de exclusión, acceso o eliminación de privacidad. Sin embargo, el tiempo de espera global garantiza que las personas nunca permanezcan más de 30 días en ningún recorrido.

Debido al tiempo de espera de recorrido de 30 días, cuando no se permite la reentrada al recorrido, no podemos asegurarnos de que el bloqueo de reentrada funcione durante más de 30 días. De hecho, al eliminar toda la información sobre las personas que ingresaron al recorrido 30 días después de su entrada, no podemos saber la persona ingresada anteriormente, hace más de 30 días.

## Zona horaria y zona horaria del perfil {#timezone}

Las zonas horarias se definen en el nivel de recorrido.

Puede introducir una zona horaria fija o utilizar perfiles de Adobe Experience Platform para definir la zona horaria de recorrido.

Para obtener más información sobre la administración de huso horario, consulte [esta página](../building-journeys/timezone-management.md).
