---
product: adobe campaign
solution: Journey Orchestration
title: Usar ações do Adobe Campaign v7/v8
description: Saiba mais sobre as ações do Adobe Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 13%

---

# Uso do Adobe Campaign v7/v8 {#using_campaign_classic}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Uma integração está disponível se você utilizar o Adobe Campaign v7 ou v8. Ele permitirá enviar emails, notificações por push e SMS usando recursos de mensagens transacionais do Adobe Campaign.

A conexão entre as instâncias do Journey Orchestration e do Campaign é configurada pela Adobe no momento do provisionamento. Entre em contato com a Adobe.

Para que isso funcione, é necessário configurar uma ação dedicada. Consulte esta [seção](../action/acc-action.md).

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-classic-use-case.md).

1. Projete sua jornada, começando com um evento. Consulte esta [seção](../building-journeys/journey.md).
1. Na seção **Ação** da paleta, selecione uma ação de Campanha e adicione-a à sua jornada.
1. Nos **Parâmetros de ação**, todos os campos esperados na carga da mensagem são exibidos. Você precisa mapear cada um desses campos com o campo que deseja usar, seja do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
