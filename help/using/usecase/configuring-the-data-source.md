---
product: adobe campaign
solution: Journey Orchestration
title: Configuración de la fuente de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso simple de recorrido
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%

---


# Configuración de la fuente de datos{#concept_ax3_bcy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También necesitamos verificar que la persona es una mujer. Esta información se almacena en la base de datos Perfil del cliente en tiempo real. El **usuario técnico** debe comprobar que esos campos están definidos en la fuente de datos integrada de Adobe Experience Platform.

Para obtener más información sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el menú superior, haga clic en la pestaña **[!UICONTROL Data Sources]** y seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. En los grupos de campos, compruebe que los campos siguientes estén seleccionados:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persona > sexo_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Save]**.

La fuente de datos ya está configurada y lista para utilizarse en el recorrido.
