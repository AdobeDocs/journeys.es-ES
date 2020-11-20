---
product: adobe campaign
solution: Journey Orchestration
title: Campos de identidad de los eventos de los journeyStep
description: Campos de identidad de los eventos de los journeyStep
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 20%

---


# Campos de identidad de los eventos de los journeyStep {#sharing-identity-fields}

Esta mezcla es específica de la función travelStepEvent: este evento está relacionado con el viaje y no tiene el mapa de identidad, que describe la identidad del perfil, si la hay.

En el caso de voyStepEvent, también es necesario agregar campos relacionados con la identidad:

## profileID

Identificador de perfil

Tipo: string

## profileNamespace

Área de nombres del identificador de perfil

Tipo: string