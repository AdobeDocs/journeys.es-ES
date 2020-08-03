---
title: Instrucción condicional (si, entonces, otra)
description: Más información sobre la instrucción condicional
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# Instrucción condicional (si, entonces, otra) {#section_cdz_lsk_w3b}

La instrucción condicional (si, por lo tanto, si no) se admite en el editor avanzado. Permite definir expresiones más complejas. Se compone de los siguientes elementos:

* **[!UICONTROL if]**:: la condición que se va a evaluar primero.
* **[!UICONTROL then]**:: la expresión que debe evaluarse en caso de que el resultado de la evaluación de la condición sea verdadero.
* **[!UICONTROL else]**:: la expresión que debe evaluarse en caso de que el resultado de la evaluación de la condición sea falso.

>[!NOTE]
>
>Se requieren paréntesis en todas las expresiones.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` debe devolver un **booleano**.

`<expression2>` y `<expression3>` debe tener el mismo tipo o tipos compatibles. Las firmas admitidas y los tipos devueltos son:

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Uso**

La instrucción condicional le permite optimizar el flujo de trabajo del viaje reduciendo el número de actividades de condición. Por ejemplo, dentro de la misma actividad de acción, puede especificar dos alternativas para una definición de campo utilizando sólo una expresión de condición.

Ejemplo de actividad de acción (para un campo que espera una cadena como resultado de la instrucción condicional):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
