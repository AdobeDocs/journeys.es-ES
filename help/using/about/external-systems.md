---
product: adobe campaign
solution: Journey Orchestration
title: Integración con sistemas externos
description: Conozca las prácticas recomendadas al integrar sistemas externos
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 6%

---

# Integración con sistemas externos {#external-systems}

Esta página presenta las diferentes protecciones proporcionadas por Journey Orchestration al integrar un sistema externo, así como las prácticas recomendadas: cómo optimizar la protección del sistema externo mediante la API de límite, cómo configurar el tiempo de espera de recorrido y cómo funcionan los reintentos.

Journey Orchestration permite configurar conexiones a sistemas externos mediante fuentes de datos y acciones personalizadas. Esto le permite, por ejemplo, enriquecer sus recorridos con datos procedentes de un sistema de reservas externo o enviar mensajes mediante un sistema de terceros como Epsilon o Facebook.

Al integrar un sistema externo, puede encontrar varios problemas, el sistema puede ser lento, puede dejar de responder o es posible que no pueda gestionar un volumen grande. Journey Orchestration ofrece varias protecciones para proteger el sistema de la sobrecarga.

Todos los sistemas externos son diferentes en términos de rendimiento. Debe adaptar la configuración a sus casos de uso.

Cuando el Journey Orchestration ejecuta una llamada a una API externa, las protecciones técnicas se ejecutan de la siguiente manera:

1. Se aplican reglas de límite: si se alcanza la tasa máxima, las llamadas restantes se descartan.

2. Tiempo de espera y reintento: si se cumple la regla de límite, el Journey Orchestration intenta realizar la llamada hasta que se alcanza el final del tiempo de espera.

## Límite{#capping}

La API de límite integrada ofrece una protección técnica ascendente que ayuda a proteger el sistema externo.

Para las fuentes de datos externas, el número máximo de llamadas por segundo se establece en 15. Si el número de llamadas supera las 15 por segundo, las llamadas restantes se descartan. Puede aumentar este límite para fuentes de datos externas privadas. Adobe de contacto para incluir el punto final en la lista de permitidos. Esto no es posible para fuentes de datos externas públicas.

Para acciones personalizadas, debe evaluar la capacidad de su API externa. Por ejemplo, si Journey Optimizer envía 1000 llamadas por segundo y su sistema solo admite 100 llamadas por segundo, debe definir una regla de límite para que el sistema no se sature.

Las reglas de límite se definen en el nivel de zona protegida para un punto de conexión específico (la dirección URL llamada ). En tiempo de ejecución, Journey Orchestration comprueba si hay una regla de límite definida y aplica la tasa definida durante las llamadas a ese extremo. Si el número de llamadas supera la tasa definida, las llamadas restantes se descartan y se contabilizan como errores en el sistema de informes.

Una regla de límite es específica para un extremo, pero global para todos los recorridos de una zona protegida. Esto significa que las ranuras de límite se comparten entre todos los recorridos de una zona protegida.

Por ejemplo, supongamos que ha definido una regla de límite de 100 llamadas por segundo para el sistema externo. Una acción personalizada llama al sistema en 10 recorridos diferentes. Si un recorrido recibe 200 llamadas por segundo, utilizará las 100 ranuras disponibles y descartará las 100 ranuras restantes. Como la velocidad máxima se ha superado, los otros 9 recorridos no tendrán ninguna ranura. Esta granularidad ayuda a proteger el sistema externo de sobrecargas y caídas.

Para obtener más información sobre la API de límite y cómo configurarlas, consulte [esta página](../api/capping.md).

## Tiempo de espera y reintentos{#timeout}

Si se cumple la regla de límite, se aplica la regla de tiempo de espera.

En cada recorrido, puede definir una duración de tiempo de espera. Esto le permite establecer una duración máxima al llamar a un sistema externo. La duración del tiempo de espera se configura en las propiedades de un recorrido. Consulte [esta página](../building-journeys/changing-properties.md#timeout_and_error).

Este tiempo de espera es global para todas las llamadas externas (llamadas a API externas en acciones personalizadas y fuentes de datos personalizadas). De forma predeterminada, se establece en 5 segundos.

Durante el tiempo de espera definido, el Journey Orchestration intenta llamar al sistema externo. Después de la primera llamada, se puede realizar un máximo de tres reintentos hasta que se alcance el final de la duración del tiempo de espera. No se puede cambiar el número de reintentos.

Cada reintento utiliza una ranura. Si tiene un límite de 100 llamadas por segundo y cada una de las llamadas requiere dos reintentos, la tasa cae a 30 llamadas por segundo (cada llamada utiliza 3 ranuras: la primera llamada y dos reintentos).

El valor de duración del tiempo de espera depende del caso de uso. Si desea enviar el mensaje rápidamente, por ejemplo, cuando el cliente entra en el almacén, no desea configurar un tiempo de espera largo. Además, cuanto más tiempo de espera sea, más elementos se pondrán en cola. Esto puede afectar en gran medida al rendimiento. Si el Journey Orchestration realiza 1000 llamadas por segundo, mantener 5 o 15 segundos de datos puede saturar rápidamente el sistema.

Veamos un ejemplo para un tiempo de espera de 5 segundos.

* La primera llamada dura menos de 5 segundos: la llamada se realiza correctamente, no se realiza ningún reintento.
* La primera llamada dura más de 5 segundos: la llamada se cancela y no hay reintento. Se cuenta como un error de tiempo de espera en los informes.
* La primera llamada falla después de 2 segundos (el sistema externo devuelve un error): quedan 3 segundos para los reintentos, si están disponibles los espacios de límite.
   * Si uno de los tres reintentos se realiza correctamente antes del final de los 5 segundos, se realiza la llamada y no hay ningún error.
   * Si se alcanza el final de la duración del tiempo de espera durante los reintentos, la llamada se cancela y se cuenta como un error de tiempo de espera en el sistema de informes.

## Preguntas frecuentes{#faq}

**¿Cómo puedo configurar una regla de límite? ¿Existe una regla de límite predeterminada?**

De forma predeterminada, no hay ninguna regla de límite. Las reglas de límite se definen en el nivel de entorno limitado para un extremo específico (la dirección URL llamada ), mediante la API de límite. Consulte [esta sección](../about/external-systems.md#capping) y [esta página](../api/capping.md).

**¿Cuántos reintentos se realizan? ¿Puedo cambiar el número de reintentos o definir un período de espera mínimo entre reintentos?**

Para una llamada determinada, se puede realizar un máximo de tres reintentos después de la primera llamada, hasta que se alcance el final de la duración del tiempo de espera. No se puede cambiar el número de reintentos ni el tiempo entre cada reintento. Consulte [esta sección](../about/external-systems.md#timeout).

**¿Dónde puedo configurar el tiempo de espera? ¿Hay un valor máximo?**

En cada recorrido, puede definir una duración de tiempo de espera. La duración del tiempo de espera se configura en las propiedades de un recorrido. La duración del tiempo de espera debe estar entre 1 segundo y 30 segundos. Consulte [esta sección](../about/external-systems.md#timeout) y [esta página](../building-journeys/changing-properties.md#timeout_and_error).
