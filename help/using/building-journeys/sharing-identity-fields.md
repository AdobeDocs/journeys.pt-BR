---
product: adobe campaign
title: campos de identidade do evento journeyStep
description: campos de identidade do evento journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 58%

---

# campos de identidade do evento journeyStep {#sharing-identity-fields}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


Este mixin é específico de journeyStepEvent: este evento está relacionado ao jornada e não tem o identityMap, que descreve a identidade do perfil, se houver.

Para journeyStepEvent, também é necessário adicionar campos relacionados à identidade:

## profileID

Identificador de perfil

Tipo: sequência de caracteres

## profileNamespace

Namespace do identificador de perfil

Tipo: sequência de caracteres
