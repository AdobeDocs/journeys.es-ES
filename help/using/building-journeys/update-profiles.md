---
product: adobe campaign
solution: Journey Orchestration
title: Saltar de un recorrido a otro
description: Saltar de un recorrido a otro
translation-type: tm+mt
source-git-commit: 5c94f64c10d12690e27585806962bf9537636e9c
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 3%

---


# Actualizar perfil {#update-profile}

La actividad de acción **[!UICONTROL Update profile]** le permite actualizar un perfil existente de Adobe Experience Platform con información proveniente del evento, una fuente de datos o con un valor específico.

## Notas importantes

* La acción **Update profile** solo se puede utilizar en recorridos que comiencen por un evento que tenga un área de nombres.
* La acción solo actualiza los campos existentes, no crea campos de perfil nuevos.
* No puede utilizar la acción **Update profile** para generar eventos de experiencia, por ejemplo una compra.
* Al igual que cualquier otra acción, puede definir una ruta alternativa en caso de error o de tiempo de espera y no puede colocar dos acciones en paralelo.
* La solicitud de actualización enviada a Platform será rápida, pero no inmediata/en un segundo. Se tardará normalmente unos segundos, pero a veces más sin garantía. Como resultado, por ejemplo, si una acción utiliza el &quot;campo 1&quot; actualizado por una acción Actualizar perfil colocada justo antes, no debería esperar que el &quot;campo 1&quot; se actualice en la acción .
* Las fuentes de datos tienen una noción de duración de la caché, a nivel de grupo de campos. Si espera aprovechar, en un recorrido, un campo de perfil actualizado recientemente, asegúrese de definir una duración de caché muy corta.

## Uso del modo de prueba {#using-the-test-mode}

En el modo de prueba, la actualización de perfil no se simulará. La actualización se realizará en el perfil de prueba.

Solo los perfiles de prueba pueden entrar en un recorrido en modo de prueba. Puede crear un nuevo perfil de prueba o convertir un perfil existente en un perfil de prueba. En Adobe Experience Platform, puede actualizar los atributos de perfil mediante llamadas a la API, pero no se pueden realizar a través de la interfaz. La forma más sencilla de hacerlo es usar una actividad de acción **Update profile** y cambiar el campo booleano del perfil de prueba de falso a verdadero.

Para obtener más información sobre el modo de prueba, consulte esta [sección](../building-journeys/testing-the-journey.md).

## Uso de la actualización de perfil

1. Diseñe el recorrido empezando por un evento. Consulte esta [sección](../building-journeys/journey.md).

1. En la sección **Action** de la paleta, suelte la actividad **Update profile** en el lienzo.

   ![](../assets/profileupdate0.png)

1. Seleccione un esquema de la lista.

1. Haga clic en **Fields** para seleccionar el campo que desea actualizar. Solo se puede seleccionar un campo.

   ![](../assets/profileupdate2.png)

1. Seleccione un conjunto de datos de la lista. La selección del conjunto de datos determinará dónde se almacenará el nuevo valor del campo de perfil.

1. Haga clic en el campo **Value** para definir el valor que desee utilizar:

   * Con el editor de expresiones simple, se puede seleccionar un campo de un origen de datos o del evento entrante.

      ![](../assets/profileupdate4.png)

   * Si desea definir un valor específico o aprovechar las funciones avanzadas, haga clic en **Advanced mode**.

      ![](../assets/profileupdate3.png)

El **perfil de actualización** ya está configurado.

![](../assets/profileupdate1.png)