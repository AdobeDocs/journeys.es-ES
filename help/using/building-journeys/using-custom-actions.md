---
product: adobe campaign
title: Uso de acciones personalizadas
description: Más información sobre las actividades de acción
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# Uso de acciones personalizadas {#section_f2c_hbg_nhb}

El panel de configuración de actividad muestra los parámetros de configuración de URL y los parámetros de autenticación configurados para la acción personalizada. [Más información](../action/about-custom-action-configuration.md).

## Configuración de URL

### Ruta dinámica

Si la dirección URL incluye una ruta dinámica, especifique la ruta en la variable **[!UICONTROL Path]** field.

>[!NOTE]
>
>No se puede configurar la parte estática de la URL en la recorrido, sino en la configuración global de la acción personalizada. [Más información](../action/about-custom-action-configuration.md).

Para concatenar campos y cadenas de texto sin formato, utilice las funciones Cadena o el signo Más (+) en el editor de expresiones avanzadas. Escriba las cadenas de texto sin formato entre comillas simples (&#39;) o dobles (&quot;). [Más información](../expression/expressionadvanced.md).

Esta tabla muestra un ejemplo de configuración:

| Campo | Valor |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Ruta | `The id of marketingCampaign + '/messages'` |

La URL concatenada tiene este formulario:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Encabezados

El **[!UICONTROL URL Configuration]** Esta sección muestra los campos de encabezado dinámicos, pero no los campos de encabezado constantes. Los campos de encabezado dinámicos son campos de encabezado HTTP cuyo valor se configura como variable. [Más información](../action/about-custom-action-configuration.md).

Si es necesario, especifique el valor de los campos de encabezado dinámico:

1. Seleccione la acción personalizada en el recorrido.
1. En el panel de configuración, haga clic en el icono de lápiz situado junto al campo de encabezado en la **[!UICONTROL URL Configuration]** sección.

   ![](../assets/journey-dynamicheaderfield.png)

1. Seleccione un campo y haga clic en **[!UICONTROL OK]**.

## Parámetros de acción

En el **[!UICONTROL Action parameters]** , verá los parámetros de mensaje definidos como _&quot;Variable&quot;_. Para estos parámetros, puede definir de dónde obtener esta información (por ejemplo: eventos, fuentes de datos), pasar valores manualmente o utilizar el editor de expresiones avanzadas para casos de uso avanzados. Los casos de uso avanzados pueden ser manipulación de datos y otro uso de funciones. [Más información](../expression/expressionadvanced.md).

**Temas relacionados**

[Configuración de una acción](../action/about-custom-action-configuration.md)
