---
product: adobe campaign
title: Esquemas de ExperienceEvent para eventos de Journey Orchestration
description: Obtenga información sobre los esquemas de ExperienceEvent para eventos de Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---

# Esquemas de ExperienceEvent para [!DNL Journey Orchestration] eventos


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._



[!DNL Journey Orchestration] eventos son eventos de experiencia XDM que se envían a Adobe Experience Platform a través de la ingesta de transmisión.

Por lo tanto, un requisito previo importante para configurar eventos para [!DNL Journey Orchestration] es que esté familiarizado con el Experience Data Model (o XDM) de Adobe Experience Platform y con cómo componer esquemas de Experience Event de XDM, así como con cómo transmitir datos con formato XDM a Adobe Experience Platform.

## Requisitos de esquema para [!DNL Journey Orchestration] eventos

El primer paso para configurar un evento para [!DNL Journey Orchestration] es asegurarse de que tiene un esquema XDM definido para representar el evento y un conjunto de datos creado para registrar instancias del evento en Adobe Experience Platform. Tener un conjunto de datos para los eventos no es estrictamente necesario, pero enviar los eventos a un conjunto de datos específico le permitirá mantener el historial de eventos de los usuarios para referencias y análisis futuros, por lo que siempre es una buena idea. Si aún no tiene un esquema y un conjunto de datos adecuados para su evento, ambas tareas se pueden realizar en la interfaz web de Adobe Experience Platform.

![](../assets/schema1.png)

Cualquier esquema XDM que se vaya a utilizar para [!DNL Journey Orchestration] eventos debe cumplir los siguientes requisitos:

* El esquema debe ser de la clase XDM ExperienceEvent.

  ![](../assets/schema2.png)

* Para los eventos generados por el sistema, el esquema debe incluir el mixin de ID de evento de orquestación. [!DNL Journey Orchestration] utiliza este campo para identificar eventos utilizados en recorridos.

  ![](../assets/schema3.png)

* Declare un campo de identidad para identificar el asunto del evento. Si no se especifica ninguna identidad, se puede utilizar un mapa de identidad. Este proceso no es recomendable.

  ![](../assets/schema4.png)

* Si desea que estos datos estén disponibles para la búsqueda más adelante en un Recorrido, marque el esquema y el conjunto de datos para el perfil.

  ![](../assets/schema5.png)

  ![](../assets/schema6.png)

* No dude en incluir campos de datos para capturar cualquier otro dato de contexto que desee incluir en el evento, como información sobre el usuario, el dispositivo desde el que se generó el evento, la ubicación o cualquier otra circunstancia significativa relacionada con el evento.

  ![](../assets/schema7.png)

  ![](../assets/schema8.png)

## Aprovechamiento de las relaciones de esquema{#leverage_schema_relationships}

Adobe Experience Platform permite definir relaciones entre esquemas para utilizar un conjunto de datos como una tabla de búsqueda para otro.

Supongamos que el modelo de datos de marca tiene un esquema que captura las compras. También tiene un esquema para el catálogo de productos. Puede capturar el ID de producto en el esquema de compra y utilizar una relación para buscar detalles de producto más completos en el catálogo de productos. Esto le permite crear un segmento para todos los clientes que compraron un portátil, por ejemplo, sin tener que enumerar explícitamente todos los ID de portátil ni capturar todos los detalles del producto en sistemas transaccionales.

Para definir una relación, debe tener un campo dedicado en el esquema de origen, en este caso el campo ID de producto en el esquema de compra. Este campo debe hacer referencia al campo de ID de producto en el esquema de destino. Las tablas de origen y destino deben estar habilitadas para los perfiles y el esquema de destino debe tener ese campo común definido como su identidad principal.

Este es el esquema del catálogo de productos habilitado para el perfil con el ID de producto definido como identidad principal.

![](../assets/schema9.png)

Este es el esquema de compra con la relación definida en el campo ID de producto.

![](../assets/schema10.png)

>[!NOTE]
>
>Obtenga más información sobre las relaciones de esquema en la [documentación de Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=es).

En Journey Orchestration, puede aprovechar todos los campos de las tablas vinculadas:

* al configurar un evento unitario, [Más información](../event/experience-event-schema.md#unitary_event_configuration)
* al usar condiciones en un recorrido, [Más información](../event/experience-event-schema.md#journey_conditions_using_event_context)
* en la personalización de acciones personalizadas, [Más información](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### Configuración de evento unitario{#unitary_event_configuration}

Los campos de esquema vinculados están disponibles en la configuración de evento unitario:

* al navegar por los campos de esquema de evento en la pantalla de configuración de evento.
* al definir una condición para eventos generados por el sistema.

![](../assets/schema11.png)

Los campos vinculados no están disponibles:

* en la fórmula de clave de evento
* en la condición de id de evento (eventos basados en reglas)

Para aprender a configurar un evento unitario, consulte esta [página](../event/about-creating.md).

### Condiciones de recorrido que utilizan el contexto de evento{#journey_conditions_using_event_context}

Puede utilizar datos de una tabla de búsqueda vinculada a un evento utilizado en un recorrido para la creación de condiciones (editor de expresiones).

Añada una condición en un recorrido, edite la expresión y despliegue el nodo de evento en el editor de expresiones.

![](../assets/schema12.png)

Para aprender a definir las condiciones de recorrido, consulte esta [página](../building-journeys/condition-activity.md).

### Personalización de acciones con contexto de evento de recorrido{#custom_action_personalization_with_journey_event_context}

Los campos vinculados están disponibles al configurar los parámetros de acción de una actividad de acción de recorrido.

![](../assets/schema13.png)

Para aprender a utilizar acciones personalizadas, consulte esta [página](../building-journeys/using-custom-actions.md).

