---
title: Campos de identidad de los eventos de los journeyStep
description: Campos de identidad de los eventos de los journeyStep
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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