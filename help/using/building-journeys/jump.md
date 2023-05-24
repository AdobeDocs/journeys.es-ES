---
product: adobe campaign
title: Saltar de un recorrido a otro
description: Saltar de un recorrido a otro
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---

# Saltar de un recorrido a otro {#jump}

El **[!UICONTROL Jump]** la actividad de acción permite insertar particulares de un recorrido a otro. Esta función le permite:

* simplificar el diseño de recorridos muy complejos dividiéndolos en varios
* generar recorridos basados en patrones de recorrido comunes y reutilizables

En el recorrido de origen, simplemente añada un **[!UICONTROL Jump]** y seleccione un recorrido de destino. Cuando el individuo entre en el **[!UICONTROL Jump]** , se envía un evento interno al primer evento del recorrido de destinatario. Si la variable **[!UICONTROL Jump]** La acción tiene éxito, el individuo continúa progresando en el recorrido. El comportamiento es similar a otras acciones.

En el recorrido de destinatario, el primer evento activado internamente por **[!UICONTROL Jump]** La actividad hará que el individuo fluya en el recorrido.

>[!NOTE]
>
>Consulte también el vídeo del tutorial [aquí](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=es)

## Ciclo de vida

Supongamos que ha agregado una **[!UICONTROL Jump]** actividad en un recorrido A a un recorrido B. El Recorrido A es el **recorrido de origen** y el recorrido B, **recorrido objetivo**.
Estos son los diferentes pasos del proceso de ejecución:

**RECORRIDO A** se activa desde un evento externo:

1. El recorrido A recibe un evento externo relacionado con un individuo.
1. El individuo llega a la **[!UICONTROL Jump]** paso.
1. El individuo es empujado al Recorrido B, y pasa a los siguientes pasos en el Recorrido A, después de la **[!UICONTROL Jump]** paso.

En el recorrido B, el primer evento se activa internamente, a través del **[!UICONTROL Jump]** actividad del recorrido A:

1. El recorrido B recibió un evento interno del Recorrido A.
1. El individuo comienza a fluir en el Recorrido B.

>[!NOTE]
>
>El recorrido B también se puede activar mediante un evento externo.

## Prácticas recomendadas y limitaciones

### Creación

* El **[!UICONTROL Jump]** la actividad solo está disponible en recorridos que utilizan un área de nombres.
* Solo puede saltar a un recorrido que utilice el mismo área de nombres que el recorrido de origen.
* No puede saltar a un recorrido que comience por un **Calificación de segmentos** evento.
* No puede tener un **[!UICONTROL Jump]** actividad y una **Calificación de segmentos** evento en el mismo recorrido.
* Puede incluir tantos **[!UICONTROL Jump]** actividades que necesite en un recorrido. Después de un **[!UICONTROL Jump]**, puede añadir cualquier actividad necesaria.
* Puede tener tantos niveles de salto como sea necesario. Por ejemplo, el Recorrido A salta al recorrido B, que salta al recorrido C, etc.
* El recorrido de destino también puede incluir tantos **[!UICONTROL Jump]** actividades según sea necesario.
* No se admiten patrones de bucle. No hay forma de vincular dos o más recorridos que crearían un bucle infinito. El **[!UICONTROL Jump]** la pantalla de configuración de actividad de impide hacerlo.

### Ejecución

* Si la variable **[!UICONTROL Jump]** Cuando se ejecuta la actividad, se activa la última versión del recorrido de destinatario.
* Como de costumbre, un individuo único solo puede estar presente una vez en el mismo recorrido. Como resultado, si el individuo insertado desde el recorrido de origen ya está en el recorrido de destino, entonces el individuo no entrará en el recorrido de destino. No se notificará ningún error en el **[!UICONTROL Jump]** actividad porque es un comportamiento normal.

## Configuración de la actividad de salto

1. Diseñe su **recorrido de origen**.

   ![](../assets/jump1.png)

1. En cualquier paso del recorrido, agregue un **[!UICONTROL Jump]** actividad, desde el **[!UICONTROL ACTIONS]** categoría. Añada una etiqueta y una descripción.

   ![](../assets/jump2.png)

1. Haga clic dentro de **Recorrido de destino** field.
La lista muestra todas las versiones de recorrido que son borradores, activos o en modo de prueba. Recorridos que utilizan un área de nombres diferente o que comienzan con una **Calificación de segmentos** Los eventos de no están disponibles. Los recorridos de destino que crearían un patrón de bucle también se filtran.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Puede hacer clic en **Abrir recorrido de destino** , a la derecha, para abrir el recorrido de destino en una pestaña nueva.

1. Seleccione el recorrido de destino al que desee saltar.
El **Primer evento** El campo se rellena previamente con el nombre del primer evento del recorrido de destino. Si el recorrido de destino incluye varios eventos, la variable **[!UICONTROL Jump]** solo se permite en el primer evento.

   ![](../assets/jump4.png)

1. El **Parámetros de acción** muestra todos los campos del evento de destino. Del mismo modo que para otros tipos de acciones, asigne cada campo con campos del evento de origen o de la fuente de datos. Esta información se pasa al recorrido de destino durante la ejecución.
1. Añada las siguientes actividades para finalizar el recorrido de origen.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >La identidad de la persona se asigna automáticamente. Esta información no es visible en la interfaz de.

Su **[!UICONTROL Jump]** La actividad está configurada. Tan pronto como su recorrido esté activo o en modo de prueba, las personas que lleguen al **[!UICONTROL Jump]** Este paso se inserta desde en el recorrido de destino.

Cuando un **[!UICONTROL Jump]** la actividad se configura en un recorrido, un **[!UICONTROL Jump]** el icono de entrada se añade automáticamente al principio del recorrido de destino. Esto le ayuda a identificar que el recorrido se puede activar externamente, pero también internamente, a partir de una **[!UICONTROL Jump]** actividad.

![](../assets/jump7.png)

## Resolución de problemas

Cuando el recorrido se publique o esté en modo de prueba, se producirán errores si:
* el recorrido de destino ya no existe
* el recorrido de destino es borrador, está cerrado o detenido
* si el primer evento del recorrido de destino ha cambiado y la asignación está dañada

![](../assets/jump6.png)
