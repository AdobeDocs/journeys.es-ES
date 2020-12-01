---
product: adobe campaign
solution: Journey Orchestration
title: Propiedades del viaje
description: Obtenga información sobre las propiedades del viaje
translation-type: tm+mt
source-git-commit: b989e167c4aa5d8ef2667442231ff8857c5f0b18
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 1%

---


# Propiedades del viaje {#journey-properties}

En el editor de expresiones avanzado, encontrará la categoría **Propiedades del viaje**, debajo de las categorías del evento y del origen de datos. Esta categoría contiene campos técnicos relacionados con el viaje de un perfil determinado. Esta es la información recuperada por el sistema de los viajes en directo, como la ID del viaje o los errores específicos encontrados.

![](../assets/journey-properties.png)

Encontrará información, por ejemplo, sobre:

* versión del viaje: uid de viaje, uid de versión de viaje, uid de instancia, etc.
* errores: captura de datos, ejecución de acciones, etc.
* paso actual, último paso actual, etc.
* perfiles descartados

Puede utilizar estos campos para generar expresiones. Durante la ejecución del viaje, los valores se recuperarán directamente del viaje.

Estos son algunos ejemplos de casos de uso:

* **Perfiles** de registro descartados: puede enviar todos los perfiles excluidos de un mensaje mediante una regla de límite a un sistema de terceros para fines de registro. Para ello, se configura una ruta en caso de tiempo de espera y error y se agrega una condición para filtrar según un tipo de error específico, por ejemplo: &quot;descartar personas mediante una regla de límite&quot;. A continuación, puede insertar los perfiles descartados en un sistema de terceros mediante una acción personalizada.

* **Alertas push enviadas en caso de error**: puede enviar una notificación a un sistema de terceros cada vez que se produzca un error en un mensaje. Para ello, configure una ruta en caso de error, agregue una condición y una acción personalizada. Puede enviar una notificación en un canal de Slack, por ejemplo, con la descripción del error encontrado.

* **Perfeccionar errores en sistema de informes** : en lugar de tener sólo una ruta para los mensajes de error, puede definir una condición por tipo de error. Esto le permitirá refinar el sistema de informes y la vista de todos los datos de tipos de error.

## Lista de campos {#journey-properties-fields}

| Categoría | Nombre del campo | Etiqueta | Descripción |
|---|---|---|------------|
| Versión de viaje | travelUID | Identificador de viaje |  |
|  | travelVersionUID | Identificador de versión de viaje |  |
|  | travelVersionName | Nombre de la versión del viaje |  |
|  | travelVersionDescription | Descripción de la versión del viaje |  |
|  | travelVersion | Versión de viaje |  |
| Instancia de Journey | instanceUID | Identificador de instancia de viaje | ID de la instancia |
|  | externalKey | Clave externa | Identificador individual que activa el viaje |
| Identidad | profileId | Identificador de identidad de perfil | Identificador del perfil en el viaje |
|  | área de nombres | Área de nombres de identidad de perfil | Área de nombres del perfil en el viaje (ejemplo: ECID) |
| Nodo actual | currentNodeId | Identificador de nodo actual | Identificador de la actividad actual (nodo) |
|  | currentNodeName | Nombre del nodo actual | Nombre de la actividad actual (nodo) |
| Nodo anterior | previousNodeId | Identificador de nodo anterior | Identificador de la actividad anterior (nodo) |
|  | previousNodeName | Nombre de nodo anterior | Nombre de la actividad anterior (nodo) |
| Errores | lastNodeUIDInError | Último identificador de nodo en error | Identificador de la última actividad (nodo) en error |
|  | lastNodeNameInError | El nombre del último nodo en el error | Nombre de la última actividad (nodo) en error |
|  | lastNodeTypeInError | Último tipo de nodo en error | Tipo de error de la última actividad (nodo) en error. Tipos posibles:<ul><li>Eventos: Eventos, Reacciones, SQL (ejemplo: Calificación del segmento)</li><li>Control de flujo: Fin, condición, espera</li><li>Acciones: acciones ACS, salto, acción personalizada</li></ul> |
|  | lastErrorCode | Último código de error | Código de error de la última actividad (nodo) en error. Posibles errores: <ul><li>Códigos de error HTTP</li><li>captado</li><li>timedOut</li><li>error (ejemplo: predeterminado en caso de error inesperado. No debería suceder o muy raramente sucede)</li></ul> |
|  | lastEjecutedActionErrorCode | Código de error de la última acción ejecutada | Código de error de la última acción en caso de error |
|  | lastDataFetchErrorCode | Código de error de la última captura de datos | Código de error de la última captura de datos desde fuentes de datos |
| Tiempo | lastActionExecutionElapsedTime | Tiempo de ejecución de la última acción transcurrido | Tiempo empleado para ejecutar la última acción |
|  | lastDataFetchElapsedTime | Último tiempo de recuperación de datos transcurrido | Tiempo empleado para ejecutar la última captura de datos desde orígenes de datos |
