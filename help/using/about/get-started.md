---
title: Introducción
description: Introducción a Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 93%

---


# Introducción{#concept_y4b_4qt_52b}

In [!DNL Journey Orchestration], there are two types of users, each of them performing specific tasks: the **technical user** and the **business user**. El acceso de los usuarios se administra mediante perfiles y derechos del producto. Consulte [](../about/access-management.md) para obtener información sobre cómo configurar el acceso de los usuarios.

Estos son los pasos principales para configurar y utilizar [!DNL Journey Orchestration]:

1. **Configurar un evento**

   Debe definir la información esperada y cómo procesarla. Esta configuración es obligatoria. Este paso lo realiza un **usuario técnico**.

   Para obtener más información, consulte [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configuración de la fuente de datos**

   Debe definir una conexión a un sistema para recuperar información adicional que se utilizará en los recorridos como, por ejemplo, en las condiciones. También se configura una fuente de datos integrada de la Experience Platform en el momento del aprovisionamiento. Este paso no es necesario si solo se aprovechan los datos de los eventos durante el recorrido. Este paso lo realiza un **usuario técnico**.

   Para obtener más información, consulte [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configuración de una acción**

   Si usa un sistema de terceros para enviar mensajes, debe configurar su conexión con [!DNL Journey Orchestration]. Consulte [](../action/about-custom-action-configuration.md).

   Si usa Adobe Campaign Standard para enviar mensajes, debe configurar la acción integrada. Consulte [](../action/working-with-adobe-campaign.md).

   Estos pasos los realiza un **usuario técnico**.

   ![](../assets/custom2.png)

1. **Diseño de un recorrido**

   Combine las distintas actividades de evento, orquestación y acción para crear sus escenarios de canal cruzado de varios pasos. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Prueba y publicación del recorrido**

   Debe validar y activar el recorrido. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte [](../building-journeys/testing-the-journey.md) y [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorización del recorrido**

   Utilice las herramientas de sistema de informes dedicadas para medir la eficacia de su recorrido. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

