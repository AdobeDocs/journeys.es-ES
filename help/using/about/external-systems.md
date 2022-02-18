---
product: adobe campaign
solution: Journey Orchestration
title: Integración con sistemas externos
description: Conozca las prácticas recomendadas al integrar sistemas externos
feature: Journeys
role: User
level: Beginner
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 1%

---

# Integración con sistemas externos {#external-systems}

Esta página presenta las diferentes protecciones proporcionadas por el Journey Orchestration al integrar un sistema externo, así como las prácticas recomendadas: cómo optimizar la protección del sistema externo mediante la API de límite, cómo configurar el tiempo de espera del recorrido y cómo funcionan los reintentos.

Journey Orchestration le permite configurar conexiones a sistemas externos mediante fuentes de datos personalizadas y acciones personalizadas. Esto le permite, por ejemplo, enriquecer sus recorridos con datos procedentes de un sistema de reservas externo o enviar mensajes mediante un sistema de terceros como Epsilon o Facebook.

Al integrar un sistema externo, puede encontrar varios problemas, el sistema puede ser lento, puede dejar de responder o puede no ser capaz de manejar un gran volumen. Journey Orchestration ofrece varias barreras para proteger su sistema de sobrecarga.

Todos los sistemas externos son diferentes en términos de rendimiento. Debe adaptar la configuración a sus casos de uso.

Cuando el Journey Orchestration ejecuta una llamada a una API externa, las protecciones técnicas se ejecutan de la siguiente manera:

1. Se aplican reglas de restricción: si se alcanza la tasa máxima, se descartan las llamadas restantes.

2. Tiempo de espera y reintento: si se cumple la regla de límite, el Journey Orchestration intenta realizar la llamada hasta que se llega al final del tiempo de espera.

## Restricción{#capping}

La API de restricción integrada ofrece una protección técnica ascendente que ayuda a proteger el sistema externo.

Para las fuentes de datos externas, el número máximo de llamadas por segundo se establece en 15. Si el número de llamadas supera los 15 por segundo, se descartan las llamadas restantes. Puede aumentar este límite para las fuentes de datos externas privadas. Póngase en contacto con el Adobe para incluir el punto final en la lista de permitidos. Esto no es posible para las fuentes de datos externas públicas.

Para las acciones personalizadas, debe evaluar la capacidad de su API externa. Por ejemplo, si Journey Optimizer envía 1000 llamadas por segundo y el sistema solo puede admitir 100 llamadas por segundo, debe definir una regla de límite para que el sistema no se satura.

Las reglas de restricción se definen en el nivel de entorno limitado para un punto final específico (la URL denominada). Durante la ejecución, el Journey Orchestration comprueba si hay una regla de límite definida y aplica la velocidad definida durante las llamadas a ese extremo. Si el número de llamadas supera la tasa definida, las llamadas restantes se descartan y se cuentan como errores en los informes.

Una regla de límite es específica para un punto final, pero global para todos los recorridos de un entorno limitado. Esto significa que las ranuras de límite se comparten entre todos los recorridos de un simulador para pruebas.

Por ejemplo, supongamos que ha definido una regla de límite de 100 llamadas por segundo para el sistema externo. Una acción personalizada llama al sistema en 10 recorridos diferentes. Si un recorrido recibe 200 llamadas por segundo, utilizará las 100 ranuras disponibles y descartará las 100 ranuras restantes. Como la velocidad máxima se ha superado, los otros 9 recorridos no tendrán ninguna ranura. Esta granularidad ayuda a proteger el sistema externo de sobrecargas y caídas.

Para obtener más información sobre la API de restricción y cómo configurar las reglas de restricción, consulte [esta página](../api/capping.md).

## Tiempo de espera y reintentos{#timeout}

Si se cumple la regla de límite, se aplica la regla de tiempo de espera.

En cada recorrido, puede definir una duración de tiempo de espera. Esto le permite establecer una duración máxima al llamar a un sistema externo. La duración del tiempo de espera se configura en las propiedades de un recorrido. Consulte [esta página](../building-journeys/changing-properties.md#timeout_and_error).

Este tiempo de espera es global para todas las llamadas externas (llamadas de API externas en acciones personalizadas y fuentes de datos personalizadas). De forma predeterminada, se establece en 5 segundos.

Durante el tiempo de espera definido, el Journey Orchestration intenta llamar al sistema externo. Después de la primera llamada, se puede realizar un máximo de tres reintentos hasta que se alcance el final del tiempo de espera. El número de reintentos no se puede cambiar.

Cada reintento utiliza una ranura. Si tiene un límite de 100 llamadas por segundo y cada una de sus llamadas requiere dos reintentos, la tasa baja a 30 llamadas por segundo (cada llamada utiliza 3 ranuras: la primera llamada y dos reintentos).

El valor de duración de tiempo de espera depende del caso de uso. Si desea enviar el mensaje rápidamente, por ejemplo, cuando el cliente entra en la tienda, no desea configurar un tiempo de espera largo. Además, cuanto más tiempo sea el tiempo de espera, más elementos se colocarán en cola. Esto puede afectar en gran medida al rendimiento. Si el Journey Orchestration realiza 1000 llamadas por segundos, mantener 5 o 15 segundos de datos puede sobrecargar rápidamente el sistema.

Veamos un ejemplo para un tiempo de espera de 5 segundos.

* La primera llamada dura menos de 5 segundos: la llamada se ha realizado correctamente y no se ha realizado ningún reintento.
* La primera llamada dura más de 5 segundos: la llamada se cancela y no hay reintento. Se cuenta como un error de tiempo de espera en los informes.
* La primera llamada falla después de 2 segundos (el sistema externo devuelve un error): Quedan 3 segundos para los reintentos, si hay ranuras de límite disponibles.
   * Si uno de los tres reintentos se realiza correctamente antes del final de los 5 segundos, la llamada se realiza y no hay error.
   * Si se alcanza el final de la duración del tiempo de espera durante los reintentos, la llamada se cancela y se cuenta como un error de tiempo de espera en los informes.

## Preguntas frecuentes{#faq}

**¿Cómo puedo configurar una regla de límite? ¿Existe una regla de límite predeterminada?**

De forma predeterminada, no hay ninguna regla de restricción. Las reglas de restricción se definen a nivel de entorno limitado para un punto final específico (la URL denominada) mediante la API de restricción. Consulte [esta sección](../about/external-systems.md#capping) y [esta página](../api/capping.md).

**¿Cuántos reintentos se realizan? ¿Puedo cambiar el número de reintentos o definir un periodo de espera mínimo entre los reintentos?**

Para una llamada determinada, se puede realizar un máximo de tres reintentos después de la primera llamada, hasta que se alcance el final de la duración del tiempo de espera. El número de reintentos y el tiempo entre cada reintento no se pueden cambiar. Consulte [esta sección](../about/external-systems.md#timeout).

**¿Dónde puedo configurar el tiempo de espera? ¿Hay un valor máximo?**

En cada recorrido, puede definir una duración de tiempo de espera. La duración del tiempo de espera se configura en las propiedades de un recorrido. La duración del tiempo de espera debe estar entre 1 segundo y 30 segundos. Consulte [esta sección](../about/external-systems.md#timeout) y [esta página](../building-journeys/changing-properties.md#timeout_and_error).