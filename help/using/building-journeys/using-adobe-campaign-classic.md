---
product: adobe campaign
solution: Journey Orchestration
title: Usar ações do Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 9cbfff4a971714a3d663ab3b761ac3e607b37cc4
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 9%

---

# Uso do Adobe Campaign Classic {#using_campaign_classic}

Uma integração estará disponível se você tiver o Adobe Campaign Classic. Ele permitirá enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign Classic.

A conexão entre as instâncias Journey Orchestration e Campaign Classic é configurada pelo Adobe no momento do provisionamento. Entre em contato com o Adobe.

Para que isso funcione, é necessário configurar uma ação dedicada. Consulte esta [seção](../action/acc-action.md).

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-classic-use-case.md).

1. Projete a jornada, começando por um evento. Consulte esta [seção](../building-journeys/journey.md).
1. Na seção **Action** da paleta, selecione uma ação Campaign Classic e adicione-a à jornada.
1. Nos **Action parameters**, todos os campos esperados na carga da mensagem são exibidos. Você precisa mapear cada um desses campos com o campo que deseja usar, do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
