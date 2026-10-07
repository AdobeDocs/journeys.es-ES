---
product: adobe campaign
title: Instrucción condicional (si, entonces, de lo contrario)
description: Obtenga información acerca de la instrucción condicional
feature: Journeys
role: Developer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 25%
---
# Instrucción condicional (si, entonces, de lo contrario) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>¿**Busca Adobe Journey Optimizer**? Haga clic [aquí](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/ajo-home){target="_blank"} para obtener la documentación de Journey Optimizer.
>
>
>_Esta documentación hace referencia a materiales de Journey Orchestration heredados que han sido reemplazados por Journey Optimizer. Póngase en contacto con su equipo de cuentas si tiene alguna pregunta sobre el acceso a Journey Orchestration o Journey Optimizer._


La instrucción condicional (if, then, else) se admite en el editor avanzado. Permite definir expresiones más complejas. Se compone de los siguientes elementos:

* **[!UICONTROL if]**: la condición que se evaluará primero.
* **[!UICONTROL then]**: la expresión que se va a evaluar en caso de que el resultado de la evaluación de la condición sea verdadero.
* **[!UICONTROL else]**: la expresión que se va a evaluar en caso de que el resultado de la evaluación de la condición sea falso.

>[!NOTE]
>
>Se requieren paréntesis alrededor de todas las expresiones.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` debe devolver un **booleano**.

`<expression2>` y `<expression3>` deben tener el mismo tipo o tipos compatibles. Las firmas admitidas y los tipos devueltos son:

```json
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
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Uso**

La instrucción condicional permite optimizar el flujo de trabajo de recorrido al reducir el número de actividades de condición. Por ejemplo, dentro de la misma actividad de acción, puede especificar dos alternativas para una definición de campo utilizando solo una expresión de condición.

Ejemplo de una actividad de acción (para un campo que espera una cadena como resultado de la instrucción condicional):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
