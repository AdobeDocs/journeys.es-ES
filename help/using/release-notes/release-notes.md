---
title: Notas de la versión
description: Más información sobre las notas de la versión
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Notas de la versión {#release-notes}

Esta página enumera todas las nuevas funciones y mejoras para la orquestación de viajes.
También puede consultar las Actualizaciones [de](../release-notes/documentation-updates.md)documentación.

## Versión del primer trimestre de 2019 {#q1-release---february-2019}

**Gestión de zonas horarias**

Las zonas horarias ahora se gestionan a nivel de viaje. Se han añadido dos parámetros en las propiedades del viaje:

![](../assets/rn-timezone.png)

* La lista desplegable **Zona horaria** le permite seleccionar una zona horaria específica. De forma predeterminada, se utiliza la zona horaria del explorador.

* La casilla **Perfil Zona horaria** le permite utilizar la zona horaria Perfil de la plataforma de experiencia de la persona que entra en el viaje, si está disponible. De lo contrario, se utilizará la zona horaria definida en la lista desplegable. Esta función no es compatible con viajes sin espacio de nombres.

**Ayuda contextual**

Ahora hay una función de ayuda contextual disponible en las distintas pantallas de orquestación de viajes. Esto significa que, con un solo clic, puede acceder directamente a la documentación sobre la funcionalidad que está utilizando actualmente.

Para mostrar la ayuda contextual, haga clic en el icono ‘i’ en la esquina superior derecha de la pantalla.

Por ahora, esta función está disponible en las pantallas de lista Inicio, Fuentes de datos, Eventos y Acciones.

**Otros cambios**

* En el modo de prueba, un nuevo parámetro permite definir el parámetro time peafiner.  las actividades de espera de tiempo pueden durar. Esto le permite acceder rápidamente a los resultados de la prueba.

* En el modo de prueba, ahora puede activar todos los eventos del viaje.


* un nuevo parámetro le permite definir el parámetro time peafiner.  las actividades de espera de tiempo pueden durar. Esto le permite acceder rápidamente a los resultados de la prueba.

* La orquestación de travesías ya está disponible en EMEA.

* Nuevo icono en la paleta para mostrar o no elementos disponibles. sans namespace. por defecto .

* lienzo, desconexión, icono petite, qui dit desconectado nodo.

* corto C ttes les listes

* IU de paleta, resultados de búsqueda de icono

* Pouvoir capper les llama a des APIS externes (fuentes de datos u acciones). marque n&#39;acepte que 500 llamadas por segundo, elle pourra mettre un topping a 500 llamadas segundos qui evite de surcharger system de lealtad

* registros del registro de pruebas. Avant status = error. Cuand en los sistemas appalle. Posibilityé de voir code erreur frase qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, niveles del sistema, código de error, respuesta de error.

* se detuvo la eliminación del viaje

* viaje: versión 1 il te met si es la última

1er mes.


## Versión de GA - Diciembre de 2019 {#ga-release---december-2019}

La orquestación de viajes es ahora GA.

Cree casos de uso de orquestación en tiempo real aprovechando los datos contextuales almacenados en eventos o fuentes de datos.

La orquestación de viajes permite la orquestación en tiempo real basada en datos contextuales de eventos, información de la plataforma de Adobe Experience o datos de servicios API de terceros. La aplicación determina en los flujos de varios pasos llamados viajes las siguientes mejores acciones específicas del consumidor, en función de su perfil y comportamiento. Esto incluye tanto el momento óptimo como el tipo de acción, como enviar al consumidor una notificación push a través de las capacidades de mensajería transaccional de Adobe Campaign Standard (requiere Adobe Campaign Standard) o la notificación de un sistema de terceros. Estas decisiones se toman en base a reglas y puntuaciones Sensei.

[Obtenga más](../action/working-with-adobe-campaign.md) información sobre la orquestación de viajes.

Recursos adicionales:

* [Tutoriales](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Comunidad](https://www.adobe.com/go/journeyorchestrationcommunity)