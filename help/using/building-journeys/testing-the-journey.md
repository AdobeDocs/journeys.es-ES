---
title: Prueba del viaje
description: 'Obtenga información sobre las pruebas de viaje '
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
source-git-commit: 25715e66b5495347e0c5ee2b1d75d44aa9cd3125

---


# Prueba del viaje{#testing_the_journey}

Antes de poder probar el viaje, debe resolver todos los errores, si los hay. Consulte [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Usted tiene la posibilidad de probar su viaje antes de su publicación, utilizando perfiles de prueba. Esto le permite analizar cómo fluyen los individuos en el viaje y solucionar los problemas antes de la publicación.

Para utilizar el modo de prueba, siga estos pasos:

1. Antes de probar el viaje, verifique que sea válido y que no haya ningún error. No podrá iniciar una prueba de un viaje con errores. Consulte [](../about/troubleshooting.md#section_h3q_kqk_fhb). Se muestra un símbolo de advertencia cuando hay errores.

1. Para activar el modo de prueba, haga clic en el **[!UICONTROL Test]** botón de alternancia, situado en la esquina superior derecha.

   ![](../assets/journeytest1.png)

1. Utilice el parámetro de tiempo de **espera en la prueba** , en la esquina inferior izquierda, para definir el tiempo que durará cada actividad de espera en el modo de prueba. El tiempo predeterminado es de 10 segundos. Esto garantizará que los resultados de la prueba se obtengan rápidamente. Este parámetro solo aparece si ha omitido una o varias actividades de espera en el viaje.

   ![](../assets/journeytest_wait.png)

1. Haga clic en **[!UICONTROL Trigger an event]** para configurar y enviar eventos al viaje. Asegúrese de enviar eventos relacionados con perfiles de prueba. Consulte [Activación de eventos](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Una vez recibidos los eventos, haga clic en el **[!UICONTROL Show log]** botón para ver el resultado de la prueba y verificarlo. Consulte [Visualización de registros](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Si hay algún error, desactive el modo de prueba, modifique el viaje y pruébelo de nuevo. Cuando la prueba sea concluyente, puede publicar el viaje. Consulte [](../building-journeys/publishing-the-journey.md).

## Notas importantes {#important_notes}

* Se proporciona una interfaz para activar eventos en el viaje probado, pero los eventos también pueden enviarse a través de sistemas de terceros como Postman.
* Sólo los individuos marcados como &quot;perfiles de prueba&quot; en el servicio de perfiles de cliente en tiempo real podrán participar en el viaje probado. El proceso para crear un perfil de prueba es el mismo que el proceso para crear un perfil en la plataforma de datos. Solo tiene que asegurarse de que el indicador de perfil de prueba sea verdadero. Puede utilizar la sección Segmentos de la interfaz de la plataforma de datos para crear un segmento de perfiles de prueba en la plataforma de datos y ver una lista no exhaustiva. La lista exhaustiva no se puede mostrar por ahora.
* El modo de prueba solo está disponible en los desplazamientos de borrador que utilizan un espacio de nombres. De hecho, el modo de prueba debe comprobar si una persona que entra en el viaje es un perfil de prueba o no y, por tanto, debe poder llegar a la plataforma de datos.
* El número máximo de perfiles de prueba que pueden entrar en un viaje durante una sesión de prueba es de 100.
* Al desactivar el modo de prueba, se vacía el trayecto de todas las personas que lo hayan introducido en el pasado o que se encuentren en él.
* Puede habilitar/deshabilitar el modo de prueba tantas veces como sea necesario.
* No se puede modificar el viaje cuando se activa el modo de prueba. En el modo de prueba, puede publicar directamente el viaje, sin necesidad de desactivar antes el modo de prueba.

## Activación de eventos {#firing_events}

El **[!UICONTROL Trigger an event]** botón permite configurar un evento que hará que una persona entre en el viaje.

Como requisito previo, debe saber qué perfiles están marcados como perfiles de prueba en la plataforma de datos. De hecho, el modo de prueba solo permite estos perfiles en el viaje y el evento debe contener una ID. El ID esperado depende de la configuración del evento. Puede ser un ECID, por ejemplo.

Si el viaje contiene varios eventos, utilice la lista desplegable para seleccionar un evento. A continuación, configure para cada evento los campos pasados y la ejecución del envío del evento. La interfaz le ayuda a pasar la información correcta en la carga útil del evento y a asegurarse de que el tipo de información es correcto. El modo de prueba guarda los últimos parámetros utilizados en una sesión de prueba para su uso posterior.

![](../assets/journeytest4.png)

La interfaz le permite pasar parámetros de evento simples. Si desea pasar colecciones u otros objetos avanzados en el evento, puede hacer clic en **[!UICONTROL Code View]** para ver el código completo de la carga útil y modificarlo. Por ejemplo, puede copiar y pegar la información del evento preparada por un usuario técnico.

![](../assets/journeytest5.png)

Un usuario técnico también puede utilizar esta interfaz para componer cargas de eventos y activar eventos sin tener que utilizar una herramienta de terceros.

## Visualización de los registros {#viewing_logs}

El **[!UICONTROL Show log]** botón permite ver los resultados de la prueba. Esta página muestra la información actual del viaje en formato JSON. Un botón permite copiar nodos completos. Debe actualizar manualmente la página para actualizar los resultados de la prueba del viaje.

![](../assets/journeytest3.png)

>[!NOTE]
>
>En los registros de prueba, en caso de error al llamar a un sistema de terceros (fuente de datos o acción), se muestran el código de error y la respuesta de error.

Se muestra el número de individuos (técnicamente, se denominan instancias) que se encuentran dentro del viaje. Esta es una información útil que se muestra para cada individuo:

* _Id_: el ID interno del individuo en el viaje. Esto se puede utilizar con fines de depuración.
* _currentstep_: el paso en el que se encuentra el individuo en el viaje. Recomendamos agregar etiquetas a las actividades para identificarlas con mayor facilidad.
* _currentstep_ > fase: el estado del viaje del individuo (en ejecución, terminado, error o tiempo de espera agotado). Consulte a continuación para obtener más información.
* _currentstep_ > _extraInfo_: descripción del error y otra información contextual.
* _externalKeys_: el valor de la fórmula clave definida en el evento.
* _richData_: los datos que el viaje ha recuperado si utiliza fuentes de datos.
* _transiciónHistory_: la lista de pasos que siguió el individuo. Para los eventos, se muestra la carga útil.

