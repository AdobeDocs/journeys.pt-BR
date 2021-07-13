---
product: adobe campaign
solution: Journey Orchestration
title: Uso de ações do Adobe Campaign v7/v8
description: Saiba mais sobre as ações do Adobe Campaign v7/v8
feature: Jornadas
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 18%

---

# Uso do Adobe Campaign v7/v8 {#using_campaign_classic}

Uma integração está disponível se você tiver o Adobe Campaign v7 ou v8. Ele permitirá enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign.

A conexão entre as instâncias do Journey Orchestration e do Campaign é configurada pela Adobe no momento do provisionamento. Entre em contato com o Adobe.

Para que isso funcione, é necessário configurar uma ação dedicada. Consulte esta [seção](../action/acc-action.md).

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-classic-use-case.md).

1. Projete a jornada, começando por um evento. Consulte esta [seção](../building-journeys/journey.md).
1. Na seção **Action** da paleta, selecione uma ação Campanha e adicione-a à jornada.
1. Nos **Action parameters**, todos os campos esperados na carga da mensagem são exibidos. Você precisa mapear cada um desses campos com o campo que deseja usar, do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
