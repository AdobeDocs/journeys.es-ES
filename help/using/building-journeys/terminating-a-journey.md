---
product: adobe campaign
title: Finalización de un recorrido
description: Obtenga información sobre cómo finalizar un recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 2d1b9d6b-0a53-436c-b251-ce77cb931aaa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 5%

---

# Finalización de un recorrido


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


Las opciones **[!UICONTROL Stop]** y **[!UICONTROL Close to new entrances]** le permiten finalizar **recorridos activos**. Cerrar un recorrido implica **que la llegada de nuevos clientes al recorrido está bloqueada** y que los clientes que ya ingresaron al recorrido pueden experimentarlo hasta el final. Esta es la forma más recomendada de poner fin a un recorrido, ya que ofrece la mejor experiencia para los clientes. Detener un recorrido implica que todas las personas que ya han entrado en un recorrido se detengan en su progreso. El recorrido está básicamente apagado.

>[!NOTE]
>
>Tenga en cuenta que no puede reanudar un recorrido cerrado o detenido.
>
>El concepto de finalización del recorrido se describe en esta [sección](../building-journeys/journey.md#ending_a_journey).

## Cierre de un recorrido

Puede cerrar un recorrido manualmente para asegurarse de que los clientes que ya han introducido el recorrido pueden finalizar su ruta, pero los nuevos usuarios no pueden entrar en el recorrido.

Cuando se cierre, un recorrido tendrá el estado **[!UICONTROL Closed (no entrance)]**. Después del tiempo de espera global predeterminado de 30 días, el recorrido cambiará al estado **Finalizado**. Consulte esta [sección](../building-journeys/changing-properties.md#entrance).

No se puede reiniciar ni eliminar una versión de recorrido cerrado. Puede crear una nueva versión del mismo o duplicarlo. Solo se pueden eliminar los recorridos finalizados.

Para cerrar un recorrido, haga clic en **[!UICONTROL Close to new entrances]** mientras pasa el ratón por encima de un recorrido en la lista de recorridos.

![](../assets/do-not-localize/journey-finish-quick-action.png)

También puede:

1. En **[!UICONTROL Home]**, haga clic en el recorrido que desee cerrar.
1. En la parte superior derecha, haga clic en la flecha hacia abajo.

   ![](../assets/finish_drop_down_list.png)

1. Haga clic en **[!UICONTROL Close to new entrances]**. Aparecerá un cuadro de diálogo.
1. Haga clic en **[!UICONTROL Close to new entrances]** para confirmar.

## Detención de un recorrido

Puede detener un recorrido cuando se ha producido una emergencia y todo el procesamiento debe finalizar inmediatamente en un recorrido.

No se puede reiniciar una versión de recorrido detenida.

Cuando se detiene, un recorrido tendrá el estado **[!UICONTROL Stopped]**.

Puede detener un recorrido (por ejemplo, si un experto en marketing se da cuenta de que el recorrido se dirige a la audiencia incorrecta o si una acción personalizada que se supone que debe enviar mensajes no funciona correctamente...) haciendo clic en **[!UICONTROL Stop]** mientras pasa el ratón sobre un recorrido de la lista de recorridos.

![](../assets/do-not-localize/journey-stop-quick-action.png)

También puede:

1. En **[!UICONTROL Home]**, haga clic en el recorrido que desee detener.
1. En la parte superior derecha, haga clic en la flecha hacia abajo.

![](../assets/finish_drop_down_list.png)

1. Haga clic en **[!UICONTROL Stop]**. Aparecerá un cuadro de diálogo.
1. Haga clic en **[!UICONTROL Stop]** para confirmar.
