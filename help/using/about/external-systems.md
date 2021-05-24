---
product: adobe campaign
solution: Journey Orchestration
title: Integración con sistemas externos
description: Conozca las prácticas recomendadas al integrar sistemas externos
feature: Recorridos
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integración con sistemas externos {#external-systems}

Esta página presenta las diferentes protecciones proporcionadas por el Journey Orchestration al integrar un sistema externo, así como las prácticas recomendadas: cómo optimizar la protección del sistema externo con la API de límite, cómo configurar el tiempo de espera de recorrido y cómo funcionan los reintentos.

Journey Orchestration le permite configurar conexiones a sistemas externos mediante fuentes de datos personalizadas y acciones personalizadas. Esto le permite, por ejemplo, enriquecer sus recorridos con datos procedentes de un sistema de reservas externo o enviar mensajes mediante sistemas de terceros como Epsilon o Facebook.

Al integrar un sistema externo, puede encontrar varios problemas, el sistema puede ser lento, puede dejar de responder o puede no ser capaz de manejar un gran volumen. Journey Orchestration ofrece varias barreras para proteger su sistema de sobrecarga.

Todos los sistemas externos son diferentes en términos de rendimiento. Debe adaptar la configuración a cada caso de uso.

Cuando el Journey Orchestration ejecuta una llamada a una API externa, las protecciones técnicas se ejecutan de la siguiente manera:

1. Restricción: se aplican reglas de restricción
2. Tiempo de espera y reintento:

## Restricción

La API de restricción integrada ofrece una protección técnica ascendente que ayudará a proteger el sistema externo. Antes, debe evaluar la capacidad de su API externa. Por ejemplo, si el Journey Orchestration envía 1000 llamadas por segundo y el sistema solo puede admitir 100 llamadas por segundo, debe definir una regla de límite para que el sistema no se satura.

Las reglas de restricción se definen en el nivel de entorno limitado para un punto final específico (la URL denominada). Durante la ejecución, el Journey Orchestration comprueba si hay una regla de límite definida y aplica la velocidad definida durante las llamadas a ese extremo. Si el número de llamadas supera la tasa definida, se descartan las llamadas restantes.

Una regla de límite es específica para un punto final, pero global para todos los recorridos de un entorno limitado. Esto significa que las ranuras de llamada se comparten entre todos los recorridos de un simulador para pruebas. Por ejemplo, supongamos que el sistema externo tiene un límite definido de 100 llamadas por segundo y se lo llama una acción personalizada en 10 recorridos diferentes. Si un recorrido recibe 200 llamadas por segundo, mantendrá las 100 ranuras disponibles y descartará las 100 ranuras restantes. Dado que la velocidad máxima ya se ha superado, los otros 9 recorridos no tendrán ninguna ranura disponible. Esta granularidad ayuda a proteger el sistema externo de sobrecargas y caídas.

Una llamada descartada debido a límites de límite se cuenta como un error en los informes.

Para aprender a configurar reglas de restricción, consulte [esta página](../api/timezone-management.md).

## Tiempo de espera y reintentos

Ensuite -> tiempo de espera definido, et qui definir le temps maximal qu&#39;on aloue a lappel au sys externe. Pendant ce temps là, en essaie de faire des appels. En fait un appel, si l&#39;appel dure moinre longtemps que le timeout ca marche, si plus longtemps on voit ca comme une timeout error, et coté reporting compabilisé com une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), reintento. 3 reintentos máx., pasar configurables. SI puede exceder el tiempo de espera global (par ejemplo 2 essais, mais depasse le timeout) erreur de timeout. plsu de temps que necesariamente. Timeout durée max qu&#39;on alloue a appel et aux retry es erreurs.

