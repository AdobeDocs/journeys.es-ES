---
product: adobe campaign
title: Instrucción condicional (if, then, else)
description: Más información sobre la instrucción condicional
feature: Recorridos
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 1%

---

# Instrucción condicional (if, then, else) {#section_cdz_lsk_w3b}

La instrucción condicional (si, entonces, si no) es compatible con el editor avanzado. Permite definir expresiones más complejas. Se compone de los siguientes elementos:

* **[!UICONTROL if]**: la condición que se va a evaluar primero.
* **[!UICONTROL then]**: la expresión que se va a evaluar en caso de que el resultado de la evaluación de la condición sea true.
* **[!UICONTROL else]**: la expresión que se va a evaluar en caso de que el resultado de la evaluación de la condición sea false.

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

`<expression1>` debe devolver un  **booleano**.

`<expression2>` y  `<expression3>` deben tener el mismo tipo o tipos compatibles. Las firmas admitidas y los tipos devueltos son:

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

La instrucción condicional permite optimizar el flujo de trabajo de recorrido al reducir el número de actividades de condición. Por ejemplo, dentro de la misma actividad de acción, puede especificar dos alternativas para una definición de campo utilizando solo una expresión de condición.

Ejemplo de una actividad de acción (para un campo que espera una cadena como resultado de la instrucción condicional):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
