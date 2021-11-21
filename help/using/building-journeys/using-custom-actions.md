---
product: adobe campaign
title: Uso de acciones personalizadas
description: Descubra más información sobre las actividades de acción
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 9%

---

# Uso de acciones personalizadas {#section_f2c_hbg_nhb}

El panel de configuración de actividad muestra los parámetros de configuración de URL y los parámetros de autenticación configurados para la acción personalizada. [Más información](../action/about-custom-action-configuration.md).

>[!NOTE]
>
>No se puede pasar una colección simple en parámetros de acción personalizados. No se admiten campos de colección más complejos (matrices de objetos).  Tenga en cuenta también que los parámetros tienen un formato esperado (por ejemplo: string, decimal, etc.). Debe tener cuidado de respetar estos formatos esperados.

## Configuración de URL

### Ruta dinámica

Si la dirección URL incluye una ruta dinámica, especifique la ruta en la **[!UICONTROL Path]** campo .

>[!NOTE]
>
>No se puede configurar la parte estática de la URL en el recorrido, sino en la configuración global de la acción personalizada. [Más información](../action/about-custom-action-configuration.md).

Para concatenar campos y cadenas de texto sin formato, utilice las funciones de cadena o el signo más (+) en el editor de expresiones avanzadas. Escriba cadenas de texto sin formato entre comillas simples (&#39;) o entre comillas dobles (&quot;). [Más información](../expression/expressionadvanced.md).

Esta tabla muestra un ejemplo de configuración:

| Campo | Valor |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Ruta | `The id of marketingCampaign + '/messages'` |

La dirección URL concatenada tiene este formulario:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Encabezados

La variable **[!UICONTROL URL Configuration]** muestra los campos del encabezado dinámico, pero no los campos del encabezado constante. Los campos de encabezado dinámico son campos de encabezado HTTP cuyo valor está configurado como variable. [Más información](../action/about-custom-action-configuration.md).

Si es necesario, especifique el valor de los campos del encabezado dinámico:

1. Seleccione la acción personalizada en el recorrido .
1. En el panel de configuración, haga clic en el icono de lápiz situado junto al campo de encabezado en la **[!UICONTROL URL Configuration]** para obtener más información.

   ![](../assets/journey-dynamicheaderfield.png)

1. Seleccione un campo y haga clic en **[!UICONTROL OK]**.

## Parámetros de acción

En el **[!UICONTROL Action parameters]** , verá los parámetros de mensaje definidos como _&quot;Variable&quot;_. Para estos parámetros, puede definir dónde obtener esta información (por ejemplo: eventos, fuentes de datos), pase valores manualmente o utilice el editor de expresiones avanzadas para casos de uso avanzados. Los casos de uso avanzados pueden ser manipulación de datos y otro uso de funciones. [Más información](../expression/expressionadvanced.md).

**Temas relacionados**

[Configuración de una acción](../action/about-custom-action-configuration.md)
