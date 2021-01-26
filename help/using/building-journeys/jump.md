---
product: adobe campaign
solution: Journey Orchestration
title: Saltar de un recorrido a otro
description: Saltar de un recorrido a otro
translation-type: tm+mt
source-git-commit: 9d8c3a2cf79f2b861aad61089a263a6a33a747b4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 3%

---


# Saltar de un recorrido a otro {#jump}

La actividad de acción **[!UICONTROL Jump]** permite insertar individuos de un recorrido a otro. Esta función le permite:

* simplificar el diseño de recorridos muy complejos dividiéndolos en varios
* generar recorridos basados en patrones de recorrido comunes y reutilizables

En el recorrido de origen, simplemente agregue una actividad **[!UICONTROL Jump]** y seleccione un recorrido de destinatario. Cuando el individuo entra en el paso **[!UICONTROL Jump]**, se envía un evento interno al primer evento del recorrido de destinatario. Si la acción **[!UICONTROL Jump]** tiene éxito, el individuo continúa avanzando en el recorrido. El comportamiento es similar al de otras acciones.

En el recorrido de destinatario, el primer evento desencadenado internamente por la actividad **[!UICONTROL Jump]** hará que el flujo individual en el recorrido sea el mismo.

>[!NOTE]
>
>Consulte también el vídeo del tutorial [aquí](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Ciclo de vida

Supongamos que ha agregado una actividad **[!UICONTROL Jump]** en un recorrido A a un recorrido B. El recorrido A es el **recorrido de origen** y el recorrido B, el **recorrido de destinatario**.
Estos son los diferentes pasos del proceso de ejecución:

**Recorrido** Ais activado desde un evento externo:

1. El recorrido A recibe un evento externo relacionado con un individuo.
1. El individuo alcanza el paso **[!UICONTROL Jump]**.
1. El individuo se inserta en el Recorrido B y pasa a los siguientes pasos en el Recorrido A, después del paso **[!UICONTROL Jump]**.

En el recorrido B, el primer evento se activa internamente, mediante la actividad **[!UICONTROL Jump]** del recorrido A:

1. El recorrido B recibió un evento interno del Recorrido A.
1. Los inicios individuales que fluyen en el Recorrido B.

>[!NOTE]
>
>El recorrido B también se puede activar mediante un evento externo.

## Prácticas recomendadas y limitaciones

### Creación

* La actividad **[!UICONTROL Jump]** sólo está disponible en recorridos que utilizan una Área de nombres.
* Solo puede saltar a un recorrido que utilice la misma Área de nombres que el recorrido de origen.
* No puede saltar a un recorrido que inicio con un evento **de calificación de segmentos**.
* No puede tener una actividad **[!UICONTROL Jump]** y un evento **de calificación de segmentos** en el mismo recorrido.
* Puede incluir tantas **[!UICONTROL Jump]** actividades como necesite en un recorrido. Después de **[!UICONTROL Jump]**, puede agregar cualquier actividad necesaria.
* Puede tener tantos niveles de salto como sea necesario. Por ejemplo, el Recorrido A le lleva al recorrido B, que le lleva al recorrido C, etc.
* El recorrido de destinatario también puede incluir tantas **[!UICONTROL Jump]** actividades como sea necesario.
* No se admiten patrones de bucle. No hay forma de vincular dos o más recorridos que puedan crear un bucle infinito. La pantalla de configuración de la actividad **[!UICONTROL Jump]** evita que haga esto.

### Ejecución

* Cuando se ejecuta la actividad **[!UICONTROL Jump]**, se activa la última versión del recorrido de destinatario.
* Como de costumbre, un individuo único sólo puede estar presente una vez en el mismo recorrido. Como resultado, si el individuo empujado del recorrido de origen ya está en el recorrido de destinatario, entonces el individuo no entrará en el recorrido de destinatario. No se registrará ningún error en la actividad **[!UICONTROL Jump]** porque es un comportamiento normal.

## Configuración de la actividad Jump

1. Diseñe su **recorrido de origen**.

   ![](../assets/jump1.png)

1. En cualquier paso del recorrido, agregue una actividad **[!UICONTROL Jump]** desde la categoría **[!UICONTROL ACTIONS]**. Añada una etiqueta y una descripción.

   ![](../assets/jump2.png)

1. Haga clic dentro del campo **recorrido de Destinatario**.
La lista muestra todas las versiones de recorrido que están en modo borrador, activo o de prueba. No están disponibles los recorridos que utilizan una Área de nombres diferente o ese inicio con un evento **de calificación de segmentos**. Los recorridos de destinatario que podrían crear un patrón de bucle también se filtran.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Puede hacer clic en el icono **Abrir recorrido de destinatario**, en el lado derecho, para abrir el recorrido de destinatario en una nueva ficha.

1. Seleccione el recorrido de destinatario al que desea saltar.
El campo **Primer evento** se rellena con el nombre del primer evento del recorrido de destinatario. Si el recorrido de destinatario incluye varios eventos, el **[!UICONTROL Jump]** sólo se permite en el primer evento.

   ![](../assets/jump4.png)

1. La sección **Parámetros de acción** muestra todos los campos del evento de destinatario. Del mismo modo que para otros tipos de acciones, asigne cada campo a campos del evento de origen o del origen de datos. Esta información se pasará al recorrido de destinatario en tiempo de ejecución.
1. Añada las siguientes actividades para finalizar el recorrido de origen.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >La identidad del individuo se asigna automáticamente. Esta información no está visible en la interfaz.

Se ha configurado la actividad **[!UICONTROL Jump]**. Tan pronto como el recorrido esté activo o en modo de prueba, las personas que alcancen el paso **[!UICONTROL Jump]** se pasarán al recorrido de destinatario.

Cuando se configura una actividad **[!UICONTROL Jump]** en un recorrido, se agrega automáticamente un icono de entrada **[!UICONTROL Jump]** al principio del recorrido de destinatario. Esto le ayuda a identificar que el recorrido se puede activar externamente pero también internamente desde una actividad **[!UICONTROL Jump]**.

![](../assets/jump7.png)

## Resolución de problemas

Cuando el recorrido se publica o está en modo de prueba, se producirán errores si:
* el recorrido de destinatario ya no existe
* el recorrido del destinatario se desplaza, se cierra o se detiene
* si el primer evento del recorrido de destinatario ha cambiado y la asignación está dañada

![](../assets/jump6.png)
