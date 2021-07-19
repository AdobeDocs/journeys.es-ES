---
product: adobe campaign
title: Propiedades del recorrido
description: Obtenga información sobre las propiedades de recorrido
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# atributos de propiedades de recorrido {#journey-properties}

En el editor de expresiones avanzadas, se encuentra la categoría **Propiedades del Recorrido**, debajo de las categorías de evento y fuente de datos. Esta categoría contiene campos técnicos relacionados con el recorrido de un perfil determinado. Esta es la información recuperada por el sistema de los recorridos activos, como el ID de recorrido o los errores específicos encontrados.

>[!NOTE]
>
>Los atributos de las propiedades de recorrido también están disponibles en el editor de expresiones simple. Consulte esta [sección](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

Encontrará información, por ejemplo, sobre:

* Versión de recorrido: uid de recorrido, uid de versión de recorrido, uid de instancia, etc.
* errores: captura de datos, ejecución de acciones, etc.
* paso actual, último paso actual, etc.
* perfiles descartados

Puede utilizar estos campos para crear expresiones. Durante la ejecución del recorrido, los valores se recuperan directamente del recorrido.

Estos son algunos ejemplos de casos de uso:

* **Registra perfiles** descartados: puede enviar todos los perfiles excluidos de un mensaje mediante una regla de límite a un sistema de terceros para fines de registro. Para ello, configure una ruta en caso de tiempo de espera y error y añada una condición para filtrar por un tipo de error específico, por ejemplo: &quot;descartar personas mediante reglas de restricción&quot;. A continuación, puede insertar los perfiles descartados en un sistema de terceros mediante una acción personalizada.

* **Enviar alertas en caso de errores**: puede enviar una notificación a un sistema de terceros cada vez que se produzca un error en un mensaje. Para ello, configure una ruta en caso de error y añada una condición y una acción personalizada. Puede enviar una notificación en un canal de Slack, por ejemplo, con la descripción del error encontrado.

* **Refine errors in reporting** : en lugar de tener solo una ruta para los mensajes de error, puede definir una condición por tipo de error. Esto le permitirá refinar los informes y ver todos los tipos de datos de errores.

## Lista de campos {#journey-properties-fields}

| Categoría | Nombre del campo | Etiqueta | Descripción |
|---|---|---|------------|
| Versión de recorrido | journeyUID | Identificador de recorrido |  |
|  | journeyVersionUID | Identificador de versión de recorrido |  |
|  | journeyVersionName | Nombre de versión de recorrido |  |
|  | journeyVersionDescription | Descripción de la versión del recorrido |  |
|  | journeyVersion | Versión de recorrido |  |
| Instancia de recorrido | instanceUID | Identificador de instancia de recorrido | ID de la instancia |
|  | externalKey | Clave externa | Identificador individual que activa el recorrido |
|  | OrganizationId | Identificador de organización | Organización de marca |
|  | sandboxName | Nombre del espacio aislado | Nombre del entorno limitado |
| Identidad | profileId | Identificador de identidad de perfil | Identificador del perfil en el recorrido |
|  | namespace | Espacio de nombres de identidad del perfil | Espacio de nombres del perfil en el recorrido (ejemplo: ECID) |
| Nodo actual | currentNodeId | Identificador de nodo actual | Identificador de la actividad actual (nodo) |
|  | currentNodeName | Nombre del nodo actual | Nombre de la actividad actual (nodo) |
| Nodo anterior | previousNodeId | Identificador de nodo anterior | Identificador de la actividad anterior (nodo) |
|  | previousNodeName | Nombre de nodo anterior | Nombre de la actividad anterior (nodo) |
| Errores | lastNodeUIDInError | Identificador de último nodo en error | Identificador de la última actividad (nodo) en error |
|  | lastNodeNameInError | Nombre del último nodo en error | Nombre de la última actividad (nodo) en error |
|  | lastNodeTypeInError | Tipo de último nodo en error | Tipo de error de la última actividad (nodo) en error. Tipos posibles:<ul><li>Eventos: Eventos, Reacciones, SQL (ejemplo: Calificación de segmentos)</li><li>Control de flujo: Fin, condición, espera</li><li>Acciones: Acciones ACS, Jump, Custom Action</li></ul> |
|  | lastErrorCode | Último código de error | Código de error de la última actividad (nodo) en error. Posibles errores: <ul><li>Códigos de error HTTP</li><li>capted</li><li>timedOut</li><li>error (ejemplo: predeterminado en caso de error inesperado. No debería/muy raramente sucede)</li></ul> |
|  | lastExecutionActionErrorCode | Código de error de la última acción ejecutada | Código de error de la última acción en caso de error |
|  | lastDataFetchErrorCode | Código de error de la última captura de datos | Código de error de la última captura de datos desde fuentes de datos |
| Fecha | lastActionExecutionElapsedTime | Tiempo transcurrido en la última ejecución de acción | Tiempo empleado para ejecutar la última acción |
|  | lastDataFetchElapsedTime | Tiempo transcurrido en la última recuperación de datos | Tiempo empleado para ejecutar la última recuperación de datos desde fuentes de datos |
