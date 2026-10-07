---
product: adobe campaign
title: Configuración de la fuente de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso simple de recorrido
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 31%
---
# Configuración de la fuente de datos{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También tenemos que comprobar si la persona es una mujer. Esta información se almacena en la base de datos de Perfil del cliente en tiempo real. El **usuario técnico** debe comprobar que esos campos están definidos en el origen de datos integrado de Adobe Experience Platform.

Para obtener información adicional sobre la configuración del origen de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el panel de menú, seleccione **[!UICONTROL Admin]**. En la sección **[!UICONTROL Data sources]**, haga clic en **[!UICONTROL Manage]**.
1. Seleccione la fuente de datos integrada de Adobe Experience Platform.

   ![](../assets/journey23.png)

1. En los grupos de campos, compruebe que los campos siguientes estén seleccionados:

   * _persona > nombre > firstName_
   * _persona > nombre > lastName_
   * _persona > sexo_
   * _correo electrónico personal > dirección_

1. Haga clic en **[!UICONTROL Save]**.

La fuente de datos está ahora configurada y lista para utilizarse en el recorrido.
