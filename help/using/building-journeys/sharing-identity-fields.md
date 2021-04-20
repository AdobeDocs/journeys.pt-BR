---
product: adobe campaign
solution: Journey Orchestration
title: campos de identidade do evento journeyStep
description: campos de identidade do evento journeyStep
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---


# campos de identidade do evento journeyStep {#sharing-identity-fields}

Esse mixin é específico para journeyStepEvent: esse evento está relacionado ao jornada e não tem o identityMap, descrevendo a identidade do perfil, se houver.

Para journeyStepEvent, também precisamos adicionar campos relacionados à identidade:

## profileID

Identificador de perfil

Tipo: string

## profileNamespace

Namespace do identificador de perfil

Tipo: string