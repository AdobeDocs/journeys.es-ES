---
title: Introducción
description: Introducción a la orquestación de viajes
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Introducción{#concept_y4b_4qt_52b}

En la orquestación de viajes, hay dos tipos de usuarios, cada uno de los cuales realiza tareas específicas: el usuario **** técnico y el usuario **** comercial. El acceso de los usuarios se administra mediante perfiles de producto y derechos. Consulte [](../about/access-management.md) para obtener información sobre cómo configurar el acceso de los usuarios.

Estos son los pasos principales para configurar y utilizar la orquestación de viajes:

1. **Configurar un evento**

   Debe definir la información esperada y cómo procesarla. Esta configuración es obligatoria. Este paso lo realiza un usuario **** técnico.

   Para obtener más información, consulte [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurar el origen de datos**

   Debe definir una conexión a un sistema para recuperar información adicional que se utilizará en los viajes, por ejemplo en las condiciones. También se configura un origen de datos integrado de la plataforma de experiencias en el momento del aprovisionamiento. Este paso no es necesario si solo aprovecha los datos de los eventos del viaje. Este paso lo realiza un usuario **** técnico.

   Para obtener más información, consulte [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurar una acción**

   Si está utilizando un sistema de terceros para enviar sus mensajes, debe configurar su conexión con la orquestación de viajes. Consulte [](../action/about-custom-action-configuration.md).

   Si utiliza Adobe Campaign Standard para enviar mensajes, debe configurar la acción integrada. Consulte [](../action/working-with-adobe-campaign.md).

   Estos pasos los realiza un usuario **** técnico.

   ![](../assets/custom2.png)

1. **Diseñe su viaje**

   Combine las diferentes actividades de evento, orquestación y acción para crear los escenarios de varios pasos entre canales. Este paso lo realiza un usuario **** comercial.

   Para obtener más información, consulte [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Probar y publicar el viaje**

   Debe validar y activar el viaje. Este paso lo realiza un usuario **** comercial.

   For more on this, see [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitoree su viaje**

   Utilice las herramientas de informes dedicadas para medir la eficacia de su viaje. Este paso lo realiza un usuario **** comercial.

   Para obtener más información, consulte [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

