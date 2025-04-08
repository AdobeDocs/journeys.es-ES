---
product: adobe campaign
title: Actualización de perfil
description: Actualización de perfil
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# Actualización de perfil {#update-profile}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._


La actividad de acción **[!UICONTROL Update profile]** le permite actualizar un perfil de Adobe Experience Platform existente con información proveniente del evento, una fuente de datos o con un valor específico.

## Notas importantes

* La acción **Actualizar perfil** solo se puede usar en recorridos que comiencen por un evento que tenga un área de nombres.
* La acción solo actualiza los campos existentes, no crea nuevos campos de perfil.
* No puede usar la acción **Actualizar perfil** para generar eventos de experiencia, por ejemplo una compra.
* Al igual que cualquier otra acción, puede definir una ruta alternativa en caso de error o tiempo de espera y no puede colocar dos acciones en paralelo.
* La solicitud de actualización enviada a Platform será rápida, pero no inmediata/en un segundo. Tardará normalmente unos segundos, pero a veces más sin garantía. Como resultado, por ejemplo, si una acción utiliza &quot;campo 1&quot; actualizado por una acción Actualizar perfil colocada justo antes, no debería esperar que &quot;campo 1&quot; se actualice en la acción.
* En el modo de prueba, la actualización de perfil no se simula. La actualización se realizará en el perfil de prueba.
* La actividad **Actualizar perfil** no admite campos XDM definidos como una enumeración.

## Uso de la actualización de perfiles

1. Diseñe su recorrido empezando con un evento. Consulte esta [sección](../building-journeys/journey.md).

1. En la sección **Acción** de la paleta, suelte la actividad **Actualizar perfil** en el lienzo.

   ![](../assets/profileupdate0.png)

1. Seleccione un esquema de la lista.

1. Haga clic en **Campos** para seleccionar el campo que desea actualizar. Solo se puede seleccionar un campo.

   ![](../assets/profileupdate2.png)

1. Seleccione un conjunto de datos de la lista.

   >[!NOTE]
   >
   >La acción **Actualizar perfil** actualiza los datos del perfil en tiempo real, pero no actualiza los conjuntos de datos. La selección del conjunto de datos es necesaria, ya que el perfil es un registro relacionado con un conjunto de datos.

1. Haga clic en el campo **Valor** para definir el valor que desea utilizar:

   * Con el editor de expresiones simple, puede seleccionar un campo de una fuente de datos o del evento entrante.

     ![](../assets/profileupdate4.png)

   * Si desea definir un valor específico o aprovechar funciones avanzadas, haga clic en **Modo avanzado**.

     ![](../assets/profileupdate3.png)

El **perfil de actualización** ya está configurado.

![](../assets/profileupdate1.png)
