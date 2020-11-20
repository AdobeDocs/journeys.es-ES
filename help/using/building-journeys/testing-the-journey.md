---
product: adobe campaign
solution: Journey Orchestration
title: Prueba del recorrido
description: 'Obtenga información sobre las pruebas de viaje '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 3%

---


# Prueba del recorrido{#testing_the_journey}

Antes de poder probar el viaje, debe resolver todos los errores, si los hay. Consulte [esta sección](../about/troubleshooting.md#section_h3q_kqk_fhb).

Usted tiene la posibilidad de probar su viaje antes de su publicación, utilizando perfiles de prueba. Esto le permite analizar cómo fluyen los individuos en el viaje y solucionar los problemas antes de la publicación.

Para utilizar el modo de prueba, siga estos pasos:

1. Antes de probar el viaje, verifique que sea válido y que no haya ningún error. No podrá iniciar una prueba de un viaje con errores. Consulte [esta sección](../about/troubleshooting.md#section_h3q_kqk_fhb). Se muestra un símbolo de advertencia cuando hay errores.

1. Para activar el modo de prueba, haga clic en el **[!UICONTROL Test]** botón de alternancia, situado en la esquina superior derecha.

   ![](../assets/journeytest1.png)

1. Utilice el **[!UICONTROL Wait time in test]** parámetro, en la esquina inferior izquierda, para definir el tiempo que durará cada actividad de espera en el modo de prueba. El valor del tiempo predeterminado es de 10 segundos. Esto garantizará que los resultados de la prueba se obtengan rápidamente. Este parámetro solo aparece si ha soltado una o más actividades de espera en el viaje.

   ![](../assets/journeytest_wait.png)

1. Haga clic en **[!UICONTROL Trigger an event]** para configurar y enviar eventos al viaje. Asegúrese de enviar eventos relacionados con los perfiles de prueba. Consulte [Disparando sus eventos](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Una vez recibidos los eventos, haga clic en el **[!UICONTROL Show log]** botón para vista del resultado de la prueba y verificarlo. Consulte [Visualización de registros](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Si hay algún error, desactive el modo de prueba, modifique el recorrido y pruebe de nuevo. Cuando la prueba sea concluyente, puede publicar el viaje. Consulte [esta página](../building-journeys/publishing-the-journey.md).

## Notas importantes {#important_notes}

* Se proporciona una interfaz para activar eventos en el viaje probado, pero también se pueden enviar eventos mediante sistemas de terceros como Postman.
* Sólo los individuos marcados como &quot;perfiles de prueba&quot; en el servicio de Perfil de clientes en tiempo real podrán participar en el viaje comprobado. Consulte [esta sección](../building-journeys/testing-the-journey.md#create-test-profile).
* El modo de prueba solo está disponible en los desplazamientos de borrador que utilizan una Área de nombres. El modo de prueba debe comprobar si una persona que entra en el viaje es un perfil de prueba o no y, por lo tanto, debe poder llegar al Adobe Experience Platform.
* El número máximo de perfiles de prueba que pueden entrar en un viaje durante una sesión de prueba es de 100.
* Al desactivar el modo de prueba, se vacía el trayecto de todas las personas que lo hayan introducido en el pasado o que se encuentren en él. También borra el sistema de informes.
* Puede habilitar/deshabilitar el modo de prueba tantas veces como sea necesario.
* No se puede modificar el viaje cuando se activa el modo de prueba. En el modo de prueba, puede publicar directamente el viaje, sin necesidad de desactivar antes el modo de prueba.

## Creating a test profile{#create-test-profile}

El proceso para crear un perfil de prueba es el mismo que cuando se crea un perfil en Adobe Experience Platform. Se realiza a través de llamadas de API. See this [page](https://docs.adobe.com/content/help/es-ES/experience-platform/profile/home.html)

Debe utilizar un esquema de Perfil que contenga la combinación &quot;detalles de la prueba de perfil&quot;. El indicador testProfile forma parte de esta combinación.

Al crear un perfil, asegúrese de pasar el valor: testprofile = true.

Tenga en cuenta que también puede actualizar un perfil existente para cambiar su indicador testProfile a &quot;true&quot;.

Este es un ejemplo de una llamada de API para crear un perfil de prueba:

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

## Disparando sus eventos {#firing_events}

El **[!UICONTROL Trigger an event]** botón permite configurar un evento que hará que una persona entre en el viaje.

>[!NOTE]
>
>Cuando se activa un evento en el modo de prueba, se genera un evento real, lo que significa que también se producirá otro viaje escuchando este evento.

Como requisito previo, debe saber qué perfiles están marcados como perfiles de prueba en Adobe Experience Platform. De hecho, el modo de prueba sólo permite estos perfiles en el viaje y el evento debe contener una identificación. El ID esperado depende de la configuración de evento. Puede ser un ECID, por ejemplo.

Si el viaje contiene varios eventos, utilice la lista desplegable para seleccionar un evento. A continuación, configure para cada evento los campos pasados y la ejecución del envío de eventos. La interfaz le ayuda a pasar la información correcta en la carga útil de evento y a asegurarse de que el tipo de información es correcto. El modo de prueba guarda los últimos parámetros utilizados en una sesión de prueba para su uso posterior.

![](../assets/journeytest4.png)

La interfaz le permite pasar parámetros de evento sencillos. Si desea pasar colecciones u otros objetos avanzados en el evento, puede hacer clic en **[!UICONTROL Code View]** para ver el código completo de la carga útil y modificarlo. Por ejemplo, puede copiar y pegar la información de evento preparada por un usuario técnico.

![](../assets/journeytest5.png)

Un usuario técnico también puede utilizar esta interfaz para componer cargas de evento y activar eventos sin tener que utilizar una herramienta de terceros.

Al hacer clic en el **[!UICONTROL Send]** botón, comienza la prueba. La progresión del individuo en el viaje se representa mediante un flujo visual. El camino se vuelve progresivamente verde a medida que el individuo se mueve a lo largo del viaje. Si se produce un error, se muestra un símbolo de advertencia en el paso correspondiente. Puede colocar el cursor sobre él para mostrar más información sobre el error y acceder a todos los detalles (cuando esté disponible).

![](../assets/journeytest6.png)

Cuando selecciona un perfil de prueba diferente en la pantalla de configuración de evento y vuelve a ejecutar la prueba, el flujo visual se borra y muestra la ruta del nuevo individuo.

Al abrir un viaje en la prueba, la ruta mostrada corresponde a la última prueba ejecutada.

El flujo visual funciona tanto si el evento se activa a través de la interfaz como externamente (por ejemplo, mediante Postman).

## Visualización de los registros {#viewing_logs}

El **[!UICONTROL Show log]** botón permite realizar vistas de los resultados de la prueba. Esta página muestra la información actual del viaje en formato JSON. Un botón permite copiar nodos completos. Debe actualizar manualmente la página para actualizar los resultados de la prueba del viaje.

![](../assets/journeytest3.png)

>[!NOTE]
>
>En los registros de prueba, en caso de error al llamar a un sistema de terceros (fuente de datos o acción), se muestran el código de error y la respuesta de error.

Se muestra el número de individuos (técnicamente, se denominan instancias) que se encuentran dentro del viaje. Esta es una información útil que se muestra para cada individuo:

* _Id_: el ID interno del individuo en el viaje. Esto se puede utilizar con fines de depuración.
* _currentstep_: el paso en el que se encuentra el individuo en el viaje. Le recomendamos que agregue etiquetas a sus actividades para identificarlas más fácilmente.
* _currentstep_ > fase: el estado del viaje del individuo (en ejecución, terminado, error o tiempo de espera agotado). Consulte a continuación para obtener más información.
* _currentstep_ > _extraInfo_: descripción del error y otra información contextual.
* _currentstep_ > _fetchErrors_: información sobre los errores de recuperación de datos que se produjeron durante este paso.
* _externalKeys_: el valor de la fórmula clave definida en el evento.
* _richData_: los datos que el viaje ha recuperado si utiliza fuentes de datos.
* _transiciónHistory_: la lista de los pasos que siguió el individuo. Para eventos, se muestra la carga útil.
* _actionExecutionErrors_ : información sobre los errores que se produjeron.

Estos son los diferentes estados del viaje de una persona:

* _Ejecutando_: la persona está en el viaje.
* _Finalizó_: la persona está al final del viaje.
* _Error_: el individuo se detiene en el viaje debido a un error.
* _Se agotó_ el tiempo de espera: el individuo es detenido en el viaje debido a un paso que tomó demasiado tiempo.

Cuando se activa un evento mediante el modo de prueba, se genera automáticamente un conjunto de datos con el nombre del origen.

Cuando se activa un evento mediante el modo de prueba, se genera automáticamente un conjunto de datos con el nombre del origen.

El modo de prueba crea automáticamente un Evento de experiencias y lo envía a Adobe Experience Platform. El nombre del origen de este Evento de experiencias es &quot;Eventos de prueba de Journey Orchestration&quot;.

En el caso de eventos múltiples activados a partir de viajes múltiples

Existe un escenario en el que se envían varios eventos desde varios viajes que tendrán diferentes Esquemas. ¿Puede un esquema asignar a un conjunto de datos? Si no es así, tendremos varios conjuntos de datos requeridos.

La creación y el nombre automáticos de estos conjuntos de datos se realiza si no se incluye un conjunto de datos de destino en el evento de experiencias. Por eso vemos hoy el &quot;Conjunto de datos creado automáticamente para voyager&quot;.

La nominación de nuestra fuente impulsa la creación automática. Si tenemos varios eventos, debemos concatenar y hacer que sea &quot;Evento de prueba Journey Orchestration - NOMBRE DEL ESQUEMA&quot;. Esto pasará automáticamente a &quot;Conjunto de datos generado automáticamente para el Evento de pruebas Journey Orchestration - NOMBRE DEL ESQUEMA&quot;.

