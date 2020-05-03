---
title: 'Acerca de los Esquemas de ExperienceEvent para Eventos de orquestación de viajes '
description: 'Obtenga información sobre los Esquemas de ExperienceEvent para los Eventos de orquestación de viajes '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606

---



# Acerca de los Esquemas de ExperienceEvent para Eventos de orquestación de viajes

Los eventos de orquestación de viajes son Eventos de experiencias XDM que se envían a Adobe Experience Platform mediante la ingestión de flujo.

Como tal, un requisito previo importante para configurar eventos para la orquestación de travesía es que esté familiarizado con el Modelo de datos de experiencia (XDM) de la plataforma y con cómo componer esquemas de XDM Experience Evento, así como con la transmisión de datos con formato XDM a la plataforma.

## Requisitos de Esquema para los Eventos de orquestación por viajes

El primer paso en la configuración de un evento para la orquestación de viajes es asegurarse de que tiene un esquema XDM definido para representar el evento y un conjunto de datos creado para registrar instancias del evento en la plataforma. Tener un conjunto de datos para sus eventos no es estrictamente necesario, pero enviar los eventos a un conjunto de datos específico le permitirá mantener el historial de eventos de los usuarios para futuras referencias y análisis, por lo que siempre es una buena idea. Si todavía no tiene un esquema y un conjunto de datos adecuados para su evento, ambas tareas se pueden realizar en la interfaz web de la plataforma.

![](../assets/schema1.png)

Cualquier esquema XDM que se vaya a utilizar para eventos de orquestación de viajes debe cumplir los siguientes requisitos:

* El esquema debe ser de la clase ExperienceEvent XDM.

![](../assets/schema2.png)

* El esquema debe incluir la combinación eventID de orquestación. La orquestación de viajes utiliza este campo para identificar los eventos utilizados en los viajes.

![](../assets/schema3.png)

* Declare un campo de identidad para identificar el sujeto del evento. Si no se especifica ninguna identidad, se puede utilizar un mapa de identidad. No se recomienda.

![](../assets/schema4.png)

* Si desea que estos datos estén disponibles para la búsqueda más adelante en un viaje, marque el esquema y el conjunto de datos para el perfil.

![](../assets/schema5.png)

![](../assets/schema6.png)

* No dude en incluir campos de datos para capturar cualquier otro dato de contexto que desee incluir con el evento, como la información sobre el usuario, el dispositivo desde el que se generó el evento, la ubicación o cualquier otra circunstancia significativa relacionada con el evento.

![](../assets/schema7.png)

![](../assets/schema8.png)