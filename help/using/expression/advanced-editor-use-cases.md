---
title: Uso del editor de expresiones avanzadas
description: Aprenda a crear expresiones avanzadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# Uso del editor de expresiones avanzadas

El editor de expresión avanzada puede utilizarse para crear condiciones que le permitan filtrar usuarios en sus viajes. Estas condiciones le permiten realizar el destinatario de los usuarios en el tiempo, la fecha, la ubicación, la duración o acciones como la compra o el abandono de carros de compras para que se puedan volver a dirigir en el viaje.

>[!NOTE]
>
>Evento inicios con @, orígenes de datos con #.

## Creación de condiciones en Eventos de experiencias

El editor de expresiones avanzado es obligatorio para realizar consultas en series temporales, como una lista de compras o clics anteriores en mensajes. Estas consultas no pueden realizarse con el editor simple.

Los eventos de experiencia se recuperan del Adobe Experience Platform como una colección en orden cronológico inverso, por lo que:

* la primera función devolverá el evento más reciente
* la última función devolverá la más antigua.

Por ejemplo: supongamos que desea enviar un destinatario a los clientes con un abandono del carro de compras en los últimos 7 días para enviar un mensaje cuando el cliente se acerque a una tienda, con una oferta de los artículos que quería que estuvieran en la tienda.

**Debe crear las siguientes condiciones:**

En primer lugar, los clientes de destinatario que navegaron por la tienda en línea pero no finalizaron el pedido en los últimos 7 días.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Esta expresión busca todos los eventos para este usuario especificados en los últimos 7 días:**

A continuación, selecciona todos los eventos de adtocart que no se transformaron en un valor completePurchase.

>[!NOTE]
>
>Para insertar campos rápidamente en la expresión, haga clic con el botón de doble en el campo del panel izquierdo del editor.

La marca de tiempo especificada actúa como el valor de fecha y hora; el segundo es el número de días.

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    AndNot(In( &quot;completePurchase&quot;, #{ExperienceExperience PlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent.all(inLastDays(currentDataPackField.timestamp, 7 )).productData
    
    
    
    
    
    .productInteraction})&quot;

Esta expresión devuelve un valor booleano.

**Ahora vamos a construir una expresión comprobando que el producto está en existencias**

* En Inventario, esta expresión busca el campo de cantidad de un producto y especifica que debe ser bueno que 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A la derecha, se especifican los valores necesarios, aquí, necesitamos recuperar la ubicación de la tienda, que se asigna desde la ubicación del evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Y especifique el SKU, utilizando la función `first` para recuperar la interacción más reciente de &quot;addToCart&quot;:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Desde allí puede agregar otra ruta en el viaje para cuando el producto no esté almacenado y enviar una notificación con oferta de participación. Configure los mensajes en consecuencia y utilice datos de personalización para mejorar el destinatario de mensajes.

## Ejemplos de manipulaciones de cadenas con el editor de expresiones avanzado

**En condiciones**

Esta condición solo recupera los eventos de geofence activados en &quot;Arlington&quot;:

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteractive
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Explicación: Se trata de una comparación estricta de cadenas (con distinción de mayúsculas y minúsculas), equivalente a una consulta en modo simple que se utiliza `equal to` con `Is sensitive` marcado.

La misma consulta con `Is sensitive` sin marcar generará la siguiente expresión en modo avanzado:

    &quot;
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteractive
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**En acciones**

La siguiente expresión le permite definir el ID de CRM en un campo de personalización de acciones:

    &quot;
    substr(@{MobileAppLaunch
    ._miorganización
    .identificación
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myOrganization
    .identity
    .crmid}
    }
    ))
    
    &quot;

Explicación: Este ejemplo utiliza `substr` y `lastIndexOf` funciones para eliminar llaves que encierran el ID de CRM pasado con un evento de inicio de aplicación móvil.

Para obtener más información sobre cómo usar el editor de expresiones avanzado, vea [este vídeo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
