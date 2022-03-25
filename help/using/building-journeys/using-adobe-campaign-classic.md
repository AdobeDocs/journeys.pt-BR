---
product: adobe campaign
solution: Journey Orchestration
title: Uso de ações do Adobe Campaign v7/v8
description: Saiba mais sobre as ações do Adobe Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 17%

---

# Uso do Adobe Campaign v7/v8 {#using_campaign_classic}

Uma integração está disponível se você tiver o Adobe Campaign v7 ou v8. Ele permitirá enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign.

A conexão entre as instâncias do Journey Orchestration e do Campaign é configurada pela Adobe no momento do provisionamento. Entre em contato com o Adobe.

Para que isso funcione, é necessário configurar uma ação dedicada. Consulte esta [seção](../action/acc-action.md).

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-classic-use-case.md).

1. Projete a jornada, começando por um evento. Veja isso [seção](../building-journeys/journey.md).
1. No **Ação** da paleta, selecione uma ação Campanha e adicione-a à jornada.
1. No **Parâmetros de ação**, todos os campos esperados no payload da mensagem são exibidos. Você precisa mapear cada um desses campos com o campo que deseja usar, do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
