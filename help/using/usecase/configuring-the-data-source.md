---
product: adobe campaign
solution: Journey Orchestration
title: Configuración de la fuente de datos
description: Obtenga información sobre cómo configurar la fuente de datos para el caso de uso sencillo del viaje
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 6%

---


# Configuración de la fuente de datos{#concept_ax3_bcy_w2b}

En nuestro caso de uso, queremos utilizar datos de personalización para nuestros mensajes. También tenemos que verificar si la persona es una mujer. Esta información se almacena en la base de datos de Perfil del cliente en tiempo real. El **usuario técnico** debe comprobar que esos campos están definidos en el origen de datos integrado de Adobe Experience Platform.

Para obtener información adicional sobre la configuración de la fuente de datos, consulte [esta página](../datasource/about-data-sources.md).

1. En el menú superior, haga clic en la ficha **[!UICONTROL Data Sources]** y seleccione el origen de datos de Adobe Experience Platform integrado.

   ![](../assets/journey23.png)

1. En los grupos de campos, compruebe que están seleccionados los siguientes campos:

   * _persona > nombre > nombre_
   * _persona > nombre > apellido_
   * _persona > sexo_
   * _personalEmail > dirección_

1. Haga clic en **[!UICONTROL Save]**.

La fuente de datos ahora está configurada y lista para utilizarse en su viaje.
