---
product: adobe campaign
title: 'Introducción '
description: Descubra los pasos principales para configurar Journey Orchestration y construir su primer recorrido.
feature: Journeys
role: User
level: Beginner
exl-id: fe7bb5fe-7b5e-46da-8ef8-ae9401522c03
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 88%

---

# Introducción{#concept_y4b_4qt_52b}


>[!CAUTION]
>
>**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con el equipo de su cuenta si tiene preguntas sobre su acceso a Journey Orchestration o Journey Optimizer._




En [!DNL Journey Orchestration], hay dos tipos de usuarios, cada uno de los cuales realiza tareas específicas: el **usuario técnico** y el **usuario empresarial**. El acceso de los usuarios se administra mediante perfiles y derechos del producto. Consulte [esta página ](../about/access-management.md) para aprender a configurar el acceso de los usuarios.

Estos son los pasos principales para configurar y utilizar [!DNL Journey Orchestration]:

1. **Configurar un evento**

   Debe definir la información esperada y cómo procesarla. Esta configuración es obligatoria. Este paso lo realiza un **usuario técnico**.

   Para obtener más información, consulte [esta página](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configuración de la fuente de datos**

   Debe definir una conexión a un sistema para recuperar información adicional que se utilizará en los recorridos como, por ejemplo, en las condiciones. También se configura una fuente de datos integrada de Adobe Experience Platform en el momento del aprovisionamiento. Este paso no es necesario si solo se aprovechan los datos de los eventos durante el recorrido. Este paso lo realiza un **usuario técnico**.

   Para obtener más información, consulte [esta página](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configuración de una acción**

   Si usa un sistema de terceros para enviar mensajes, debe configurar su conexión con [!DNL Journey Orchestration]. Consulte [esta página](../action/about-custom-action-configuration.md).

   Si usa Adobe Campaign Standard para enviar mensajes, debe configurar la acción integrada. Consulte [esta página](../action/working-with-adobe-campaign.md).

   Estos pasos los realiza un **usuario técnico**.

   ![](../assets/custom2.png)

1. **Diseño de un recorrido**

   Combine las distintas actividades de evento, orquestación y acción para crear sus escenarios de canal cruzado de varios pasos. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte [esta página](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Prueba y publicación del recorrido**

   Debe validar y activar el recorrido. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte las páginas [Prueba del recorrido](../building-journeys/testing-the-journey.md) y [Publicación del recorrido](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorización del recorrido**

   Utilice las herramientas de sistema de informes dedicadas para medir la eficacia de su recorrido. Este paso lo realiza un **usuario empresarial**.

   Para obtener más información, consulte [esta página](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)
