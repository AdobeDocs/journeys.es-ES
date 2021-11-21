---
product: adobe campaign
title: Configuración de la fuente de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso simple de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 6%

---

# Configuración de la fuente de datos{#concept_ax3_bcy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También necesitamos verificar que la persona es una mujer. Esta información se almacena en la base de datos Perfil del cliente en tiempo real. La variable **usuario técnico** debe comprobar que esos campos están definidos en la fuente de datos integrada de Adobe Experience Platform.

Para obtener información adicional sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el panel de menú, seleccione **[!UICONTROL Admin]**. En el **[!UICONTROL Data sources]** , haga clic en **[!UICONTROL Manage]**.
1. Seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. En los grupos de campos, compruebe que los campos siguientes estén seleccionados:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persona > sexo_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Save]**.

La fuente de datos ya está configurada y lista para utilizarse en el recorrido.
