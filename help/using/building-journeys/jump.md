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
ht-degree: 4%

---

# Saltar de un recorrido a otro {#jump}

La variable **[!UICONTROL Jump]** la actividad de acción permite insertar a los usuarios de un recorrido a otro. Esta función le permite:

* simplificar el diseño de recorridos muy complejos dividiéndolos en varios
* generar recorridos basados en patrones de recorrido comunes y reutilizables

En el recorrido de origen, simplemente agregue una **[!UICONTROL Jump]** y seleccione un recorrido de destino. Cuando el individuo introduce la variable **[!UICONTROL Jump]** , se envía un evento interno al primer evento del recorrido de destino. Si la variable **[!UICONTROL Jump]** la acción es exitosa, el individuo sigue progresando en el recorrido. El comportamiento es similar al de otras acciones.

En el recorrido de destino, el primer evento activado internamente por la variable **[!UICONTROL Jump]** actividad hará que el flujo individual en el recorrido sea variable.

>[!NOTE]
>
>Consulte también el vídeo del tutorial [here](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=es)

## Ciclo de vida

Supongamos que ha añadido un **[!UICONTROL Jump]** actividad en un recorrido A a un recorrido B. El Recorrido A es la **recorrido de origen** y el recorrido B, **recorrido de target**.
Estos son los diferentes pasos del proceso de ejecución:

**Recorrido A** se activa desde un evento externo:

1. El recorrido A recibe un evento externo relacionado con una persona.
1. El individuo alcanza la variable **[!UICONTROL Jump]** paso a paso.
1. El individuo se empuja al Recorrido B y pasa a los siguientes pasos del Recorrido A, después del **[!UICONTROL Jump]** paso a paso.

En el recorrido B, el primer evento se activa internamente, a través del **[!UICONTROL Jump]** actividad del recorrido A:

1. El recorrido B recibió un evento interno del Recorrido A.
1. El individuo empieza a fluir en el Recorrido B.

>[!NOTE]
>
>El recorrido B también se puede activar mediante un evento externo.

## Prácticas recomendadas y limitaciones

### Creación

* La variable **[!UICONTROL Jump]** actividad solo está disponible en recorridos que utilizan un espacio de nombres.
* Solo puede saltar a un recorrido que utilice el mismo espacio de nombres que el recorrido de origen.
* No puede saltar a un recorrido que comience por un **Clasificación del segmento** evento.
* No puede tener un **[!UICONTROL Jump]** actividad y **Clasificación del segmento** en el mismo recorrido.
* Puede incluir tantos **[!UICONTROL Jump]** actividades como necesite en un recorrido. Después de un **[!UICONTROL Jump]**, puede añadir cualquier actividad que necesite.
* Puede tener tantos niveles de salto como sea necesario. Por ejemplo, el Recorrido A salta al recorrido B, que salta al recorrido C, etc.
* El recorrido de destino también puede incluir tantos **[!UICONTROL Jump]** actividades según sea necesario.
* No se admiten patrones de bucle. No hay forma de vincular dos o más recorridos, lo que crearía un bucle infinito. La variable **[!UICONTROL Jump]** la pantalla de configuración de actividad impide que lo haga.

### Ejecución

* Cuando la variable **[!UICONTROL Jump]** se ejecuta, se activa la última versión del recorrido de destino.
* Como de costumbre, un individuo único solo puede estar presente una vez en un mismo recorrido. Como resultado, si el individuo empujado desde el recorrido de origen ya está en el recorrido de destino, el individuo no ingresará al recorrido de destino. No se notificará ningún error en la variable **[!UICONTROL Jump]** porque es un comportamiento normal.

## Configuración de la actividad Jump

1. Diseñe su **recorrido de origen**.

   ![](../assets/jump1.png)

1. En cualquier paso del recorrido, añada un **[!UICONTROL Jump]** de **[!UICONTROL ACTIONS]** categoría. Añada una etiqueta y una descripción.

   ![](../assets/jump2.png)

1. Haga clic dentro del **Recorrido de Target** campo .
La lista muestra todas las versiones de recorrido en borrador, activas o en modo de prueba. Recorridos que utilizan un área de nombres diferente o que comienzan con un **Clasificación del segmento** no están disponibles. Los recorridos de destino que podrían crear un patrón de bucle también se filtran.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Puede hacer clic en el botón **Abrir el recorrido de destino** , en el lado derecho, para abrir el recorrido de destino en una nueva pestaña.

1. Seleccione el recorrido de destino al que desee ir.
La variable **Primer evento** se rellena previamente con el nombre del primer evento del recorrido de destino. Si el recorrido de destino incluye varios eventos, la variable **[!UICONTROL Jump]** solo se permite en el primer evento.

   ![](../assets/jump4.png)

1. La variable **Parámetros de acción** muestra todos los campos del evento de destino. Del mismo modo que para otros tipos de acciones, asigne cada campo con campos del evento de origen o del origen de datos. Esta información se pasa al recorrido de destino durante la ejecución.
1. Agregue las siguientes actividades para finalizar el recorrido de origen.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >La identidad del individuo se asigna automáticamente. Esta información no está visible en la interfaz de .

Su **[!UICONTROL Jump]** actividad está configurada. Tan pronto como su recorrido esté activo o en modo de prueba, las personas que llegan al **[!UICONTROL Jump]** se insertará desde al recorrido de destino.

Cuando **[!UICONTROL Jump]** actividad está configurada en un recorrido, un **[!UICONTROL Jump]** el icono de entrada se añade automáticamente al principio del recorrido de destino. Esto le ayuda a identificar que el recorrido se puede activar externamente pero también internamente desde un **[!UICONTROL Jump]** actividad.

![](../assets/jump7.png)

## Resolución de problemas

Cuando se publica el recorrido o en modo de prueba, se producen errores si:
* el recorrido de destino ya no existe
* el recorrido de destino es borrador, cerrado o detenido
* si el primer evento del recorrido de destino ha cambiado y la asignación está dañada

![](../assets/jump6.png)
