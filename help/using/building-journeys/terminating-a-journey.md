---
product: adobe campaign
title: Finalización de un recorrido
description: Obtenga información sobre cómo finalizar un recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 2d1b9d6b-0a53-436c-b251-ce77cb931aaa
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 7%

---

# Finalización de un recorrido

La variable **[!UICONTROL Stop]** y **[!UICONTROL Close to new entrances]** las opciones permiten finalizar **live** recorridos. El cierre de un recorrido implica **que la llegada de nuevos clientes al recorrido está bloqueada** y que los clientes que ya han entrado en el recorrido pueden experimentarlo hasta el final. Esta es la forma más recomendada de poner fin a un recorrido, ya que ofrece la mejor experiencia para los clientes. Detener un recorrido implica que a las personas que ya entraron en un recorrido se les detiene en su progreso. Básicamente el recorrido está apagado.

>[!NOTE]
>
>Tenga en cuenta que no puede reanudar un recorrido cerrado o detenido.
>
>El concepto de fin de recorrido se describe en [sección](../building-journeys/journey.md#ending_a_journey).

## Cierre de un recorrido

Puede cerrar un recorrido manualmente para asegurarse de que los clientes que ya han entrado en el recorrido puedan finalizar su ruta, pero que los nuevos usuarios no puedan entrar en el recorrido.

Cuando se cierre, un recorrido tendrá el estado **[!UICONTROL Closed (no entrance)]**. Después del tiempo de espera global predeterminado de 30 días, el recorrido cambiará a la variable **Finalizado** estado. Consulte esta [sección](../building-journeys/changing-properties.md#entrance).

No se puede reiniciar ni eliminar una versión de recorrido cerrada. Puede crear una nueva versión o duplicarla. Solo se pueden eliminar los recorridos finalizados.

Para cerrar un recorrido, haga clic en **[!UICONTROL Close to new entrances]** al pasar el ratón por encima de un recorrido en la lista de recorridos.

![](../assets/do-not-localize/journey-finish-quick-action.png)

También puede:

1. En **[!UICONTROL Home]**, haga clic en el recorrido que desee cerrar.
1. En la parte superior derecha, haga clic en la flecha abajo.

   ![](../assets/finish_drop_down_list.png)

1. Haga clic en **[!UICONTROL Close to new entrances]**. Aparecerá un cuadro de diálogo.
1. Haga clic en **[!UICONTROL Close to new entrances]** para confirmar.

## Detención de un recorrido

Puede detener un recorrido cuando se produzca una emergencia y todo el procesamiento debe finalizar inmediatamente en un recorrido.

No se puede reiniciar una versión de recorrido detenida.

Cuando se detiene, un recorrido tendrá el estado **[!UICONTROL Stopped]**.

Puede detener un recorrido (por ejemplo, si un especialista en marketing se da cuenta de que el recorrido está dirigido a una audiencia incorrecta o si una acción personalizada que supuestamente debe enviar mensajes no funciona correctamente...) haciendo clic en **[!UICONTROL Stop]** al pasar el ratón por encima de un recorrido en la lista de recorridos.

![](../assets/do-not-localize/journey-stop-quick-action.png)

También puede:

1. En **[!UICONTROL Home]**, haga clic en el recorrido que desee detener.
1. En la parte superior derecha, haga clic en la flecha abajo.

![](../assets/finish_drop_down_list.png)

1. Haga clic en **[!UICONTROL Stop]**. Aparecerá un cuadro de diálogo.
1. Haga clic en **[!UICONTROL Stop]** para confirmar.
