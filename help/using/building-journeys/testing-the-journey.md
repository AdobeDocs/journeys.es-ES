---
product: adobe campaign
title: Prueba del recorrido
description: Obtenga información sobre las pruebas de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 4%

---

# Prueba del recorrido{#testing_the_journey}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


Antes de poder probar el recorrido, debe resolver todos los errores. Consulte [esta sección](../about/troubleshooting.md#section_h3q_kqk_fhb).

Puede probar el recorrido antes de su publicación mediante perfiles de prueba. Esto permite analizar el flujo de los particulares en el recorrido y solucionar los problemas antes de la publicación.

Solo los perfiles de prueba pueden introducir un recorrido en el modo de prueba. Puede crear un nuevo perfil de prueba o convertir un perfil existente en un perfil de prueba. Consulte esta [sección](../building-journeys/creating-test-profiles.md).

Para utilizar el modo de prueba, siga estos pasos:

1. Antes de probar el recorrido, compruebe que es válido y que no hay error. No podrá iniciar una prueba de un recorrido con errores. Ver [esta sección](../about/troubleshooting.md#section_h3q_kqk_fhb). Se muestra un símbolo de advertencia cuando hay errores.

1. Para activar el modo de prueba, haga clic en la opción **[!UICONTROL Test]**, que se encuentra en la esquina superior derecha.

   ![](../assets/journeytest1.png)

1. Utilice el parámetro **[!UICONTROL Wait time]**, en la esquina inferior izquierda, para definir el tiempo que cada actividad de espera y tiempo de espera de evento durará en el modo de prueba. El tiempo predeterminado es 10 segundos para esperas y tiempos de espera de evento. Esto garantizará que obtenga los resultados de la prueba rápidamente. Este parámetro solo aparece si ha colocado una o más actividades de espera en el recorrido.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Cuando se utiliza un evento de reacción con un tiempo de espera en un recorrido, el tiempo de espera predeterminado y el valor mínimo son 40 segundos. Consulte [esta sección](../building-journeys/reaction-events.md).

1. Haga clic en **[!UICONTROL Trigger an event]** para configurar y enviar eventos al recorrido.

   ![](../assets/journeyuctest1.png)

1. Configure los diferentes campos esperados. En el campo **Identificador de perfil**, escriba el valor del campo usado para identificar el perfil de prueba. Puede ser la dirección de correo electrónico, por ejemplo. Asegúrese de enviar eventos relacionados con los perfiles de prueba. Consulte [Activación de eventos](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Una vez recibidos los eventos, haga clic en el botón **[!UICONTROL Show log]** para ver el resultado de la prueba y verificarlo. Ver [Visualización de registros](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Si hay algún error, desactive el modo de prueba, modifique el recorrido y pruebe de nuevo. Cuando la prueba sea concluyente, puede publicar el recorrido. Consulte [esta página](../building-journeys/publishing-the-journey.md).

## Notas importantes {#important_notes}

* Se proporciona una interfaz para activar eventos en el recorrido probado, pero los eventos también se pueden enviar mediante sistemas de terceros como Postman.
* Solo se permite a las personas marcadas como &quot;perfiles de prueba&quot; en el servicio Perfil del cliente en tiempo real entrar en el recorrido probado. Consulte esta [sección](../building-journeys/creating-test-profiles.md).
* El modo de prueba solo está disponible en recorridos de borrador que utilizan un área de nombres. El modo de prueba debe comprobar si una persona que entra en el recorrido es un perfil de prueba o no y, por lo tanto, debe poder acceder a Adobe Experience Platform.
* El número máximo de perfiles de prueba que puede introducir un recorrido durante una sesión de prueba es de 100.
* Al deshabilitar el modo de prueba, se vacían las recorridos de todas las personas que lo ingresaron en el pasado o que se encuentran actualmente en él. También borra la creación de informes.
* Puede habilitar/deshabilitar el modo de prueba tantas veces como sea necesario.
* No puede modificar el recorrido cuando el modo de prueba está activado. En el modo de prueba, puede publicar directamente el recorrido, sin necesidad de desactivar el modo de prueba antes.
* Al llegar a una división, siempre se elige la rama superior. Puede reorganizar la posición de las ramas divididas si desea que la prueba elija una ruta diferente.
* Para optimizar el rendimiento y evitar el uso de recursos obsoletos, todos los recorridos del modo de prueba que no se hayan activado durante una semana volverán al estado Borrador.

## Conversión de un perfil en un perfil de prueba{#turning-profile-into-test}

Puede convertir un perfil existente en un perfil de prueba. En Adobe Experience Platform, puede actualizar los atributos de los perfiles mediante llamadas a la API, pero esto no se puede realizar a través de la interfaz.

La forma más sencilla de hacerlo es usando una actividad de acción **Actualizar perfil** y cambiar el campo booleano del perfil de prueba de falso a verdadero. Consulte [esta sección](../building-journeys/update-profiles.md#using-the-test-mode).

## Creación de un perfil de prueba{#create-test-profile}

Si desea crear un nuevo perfil de prueba, el procedimiento es el mismo que al crear un perfil en Adobe Experience Platform. Se realiza mediante llamadas a la API. Ver esta [página](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es)

Debe utilizar un esquema de perfil que contenga la mezcla &quot;detalles de prueba de perfil&quot;. El indicador testProfile forma parte de este mixin.

Al crear un perfil, asegúrese de pasar el valor: testProfile = true.

Tenga en cuenta que también puede actualizar un perfil existente para cambiar su indicador testProfile a &quot;true&quot;.

Este es un ejemplo de llamada de API para crear un perfil de prueba:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Activación de eventos {#firing_events}

El botón **[!UICONTROL Trigger an event]** le permite configurar un evento que hará que una persona entre al recorrido.

>[!NOTE]
>
>Cuando se almacena en déclencheur un evento en modo de prueba, se genera un evento real, lo que significa que también se producirá un recorrido que escuche este evento.

Como requisito previo, debe saber qué perfiles están marcados como perfiles de prueba en Adobe Experience Platform. De hecho, el modo de prueba solo permite estos perfiles en la recorrido y el evento debe contener un ID. El ID esperado depende de la configuración del evento. Puede ser un ECID o una dirección de correo electrónico, por ejemplo. El valor de esta clave debe agregarse en el campo **Identificador de perfil**.

>[!NOTE]
>
>Se muestra un menú desplegable para los campos que esperan una enumeración. Simplemente, seleccione uno de los valores disponibles.

Si el recorrido contiene varios eventos, utilice el menú desplegable para seleccionar un evento. A continuación, para cada evento, configure los campos pasados y la ejecución del envío del evento. La interfaz de le ayuda a pasar la información correcta en la carga útil de evento y a asegurarse de que el tipo de información es correcto. El modo de prueba guarda los últimos parámetros utilizados en una sesión de prueba para su uso posterior.

![](../assets/journeytest4.png)

La interfaz de le permite pasar parámetros de evento simples. Si desea pasar colecciones u otros objetos avanzados en el evento, puede hacer clic en **[!UICONTROL Code View]** para ver todo el código de la carga útil y modificarlo. Por ejemplo, puede copiar y pegar información de evento preparada por un usuario técnico.

![](../assets/journeytest5.png)

Un usuario técnico también puede utilizar esta interfaz para componer cargas útiles de eventos y eventos de déclencheur sin tener que utilizar una herramienta de terceros.

Al hacer clic en el botón **[!UICONTROL Send]**, comienza la prueba. La progresión del individuo en el recorrido se representa mediante un flujo visual. El camino se vuelve verde progresivamente a medida que el individuo se mueve a través del recorrido. Si se produce un error, se muestra un símbolo de advertencia en el paso correspondiente. Puede colocar el cursor sobre él para mostrar más información sobre el error y acceder a los detalles completos (cuando estén disponibles).

![](../assets/journeytest6.png)

Cuando se selecciona un perfil de prueba diferente en la pantalla de configuración de evento y se vuelve a ejecutar la prueba, el flujo visual se borra y muestra la ruta del nuevo individuo.

Al abrir un recorrido en prueba, la ruta mostrada corresponde a la última prueba ejecutada.

El flujo visual funciona independientemente de si el evento se activa a través de la interfaz o de forma externa (por ejemplo, mediante Postman).

## Modo de prueba para recorridos basados en reglas {#test-rule-based}

El modo de prueba también está disponible para recorridos que utilizan un evento basado en reglas. Para obtener más información sobre los eventos basados en reglas, consulte [esta página](../event/about-events.md).

Al activar un evento, la pantalla **Configuración de evento** le permite definir los parámetros de evento que se pasarán en la prueba. Para ver la condición de ID de evento, haga clic en el icono de información de objeto en la esquina superior derecha. También hay disponible información del objeto junto a cada campo que forma parte de la evaluación de reglas.

![](../assets/alpha-event8.png)

Para obtener más información sobre cómo usar el modo de prueba, consulte [esta página](../building-journeys/testing-the-journey.md).

## Visualización de los registros {#viewing_logs}

El botón **[!UICONTROL Show log]** le permite ver los resultados de la prueba. Esta página muestra la información actual del recorrido en formato JSON. Un botón permite copiar nodos completos. Debe actualizar manualmente la página para actualizar los resultados de la prueba del recorrido.

![](../assets/journeytest3.png)

>[!NOTE]
>
>En los registros de prueba, en caso de error al llamar a un sistema de terceros (fuente de datos o acción), se muestran el código de error y la respuesta de error.

Se muestra el número de individuos (técnicamente, se denominan instancias) que están actualmente dentro del recorrido. Esta es una información útil que se muestra para cada individuo:

* _Id_: el ID interno del individuo en la recorrido. Se puede utilizar con fines de depuración.
* _currentstep_: el paso en el que se encuentra el individuo en el recorrido. Recomendamos añadir etiquetas a las actividades para identificarlas más fácilmente.
* _currentstep_ > phase: el estado del recorrido del individuo (en ejecución, finalizado, error o tiempo de espera agotado). Consulte a continuación para obtener más información.
* _currentstep_ > _extraInfo_: descripción del error y otra información contextual.
* _currentstep_ > _fetchErrors_: información sobre errores de datos de recuperación que se produjeron durante este paso.
* _externalKeys_: el valor de la fórmula clave definida en el evento.
* _richData_: los datos que el recorrido ha recuperado si el recorrido usa orígenes de datos.
* _transitionHistory_: la lista de pasos que siguió el individuo. Para los eventos, se muestra la carga útil.
* _actionExecutionErrors_ : información sobre los errores que se produjeron.

Estos son los diferentes estados del recorrido de un individuo:

* _En ejecución_: el individuo se encuentra actualmente en el recorrido.
* _Finalizado_: el individuo se encuentra al final del recorrido.
* _Error_: el individuo se detuvo en el recorrido debido a un error.
* _Se agotó el tiempo de espera_: el individuo se detuvo en el recorrido debido a un paso que tomó demasiado tiempo.

Cuando se activa un evento con el modo de prueba, se genera automáticamente un conjunto de datos con el nombre del origen.

Cuando se activa un evento con el modo de prueba, se genera automáticamente un conjunto de datos con el nombre del origen.

El modo de prueba crea automáticamente un Evento de experiencia y lo envía a Adobe Experience Platform. El nombre de la fuente para este evento de experiencia es &quot;Eventos de prueba de Journey Orchestration&quot;.
