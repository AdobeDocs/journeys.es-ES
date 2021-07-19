---
product: adobe campaign
title: 'Esquemas de ExperienceEvent para eventos de Journey Orchestration '
description: 'Obtenga información sobre los esquemas de ExperienceEvent para eventos de Journey Orchestration '
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Esquemas de ExperienceEvent para eventos [!DNL Journey Orchestration]

[!DNL Journey Orchestration] los eventos son eventos de experiencia XDM que se envían a Adobe Experience Platform mediante la ingesta de flujo.

Por lo tanto, un requisito previo importante para configurar eventos para [!DNL Journey Orchestration] es que esté familiarizado con el Modelo de datos de experiencia de Adobe Experience Platform (o XDM) y con cómo componer esquemas de eventos de experiencia XDM, así como con cómo transmitir datos con formato XDM a Adobe Experience Platform.

## Requisitos de esquema para eventos [!DNL Journey Orchestration]

El primer paso para configurar un evento para [!DNL Journey Orchestration] es asegurarse de que tiene un esquema XDM definido para representar el evento y un conjunto de datos creado para registrar instancias del evento en Adobe Experience Platform. Tener un conjunto de datos para sus eventos no es estrictamente necesario, pero enviar los eventos a un conjunto de datos específico le permitirá mantener el historial de eventos de los usuarios para futuras referencias y análisis, por lo que siempre es una buena idea. Si aún no tiene un esquema y un conjunto de datos adecuados para el evento, ambas tareas se pueden realizar en la interfaz web de Adobe Experience Platform.

![](../assets/schema1.png)

Cualquier esquema XDM que se utilice para eventos [!DNL Journey Orchestration] debe cumplir los siguientes requisitos:

* El esquema debe pertenecer a la clase XDM ExperienceEvent .

   ![](../assets/schema2.png)

* Para los eventos generados por el sistema, el esquema debe incluir la mezcla eventID de organización. [!DNL Journey Orchestration] utiliza este campo para identificar eventos utilizados en recorridos.

   ![](../assets/schema3.png)

* Declare un campo de identidad para identificar el asunto del evento. Si no se especifica ninguna identidad, se puede utilizar un mapa de identidad. Este proceso no es recomendable.

   ![](../assets/schema4.png)

* Si desea que estos datos estén disponibles para la búsqueda más adelante en un Recorrido, marque el esquema y el conjunto de datos para el perfil.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* No dude en incluir campos de datos para capturar cualquier otro dato de contexto que desee incluir con el evento, como información sobre el usuario, el dispositivo desde el cual se generó el evento, la ubicación o cualquier otra circunstancia significativa relacionada con el evento.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)
