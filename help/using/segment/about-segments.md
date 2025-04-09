---
product: adobe campaign
title: Sobre segmentos do Adobe Experience Platform
description: Saiba como configurar um segmento do Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 7%

---

# Sobre segmentos do Adobe Experience Platform {#about-segments}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Se você estiver usando o [Serviço de Segmentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR) para criar seus segmentos, poderá aproveitá-los no [!DNL Journey Orchestration]. Graças a uma atividade de evento dedicada, você pode fazer com que os indivíduos entrem ou avancem em uma jornada com base nas entradas e saídas do segmento do Adobe Experience Platform. Isso também permite criar condições complexas em suas jornadas usando o editor de expressão simples ou avançado.

Digamos que você tenha um segmento de &quot;cliente prata&quot;. Com essa atividade, você pode fazer com que todos os novos clientes Silver insiram uma jornada e enviem a eles uma série de mensagens personalizadas. Você também pode criar condições facilmente com base nesse segmento.

Estas são as possibilidades que [!DNL Journey Orchestration] oferece a você com segmentos:

* Acesse a lista de segmentos do Adobe Experience Platform. Consulte [Criando um segmento](../segment/creating-a-segment.md).
* Crie segmentos diretamente no [!DNL Journey Orchestration] da mesma maneira que você os cria usando o Serviço de segmentação. Consulte [Criando um segmento](../segment/creating-a-segment.md).
* Aproveite os segmentos nas condições da sua jornada usando o editor de expressão simples ou avançado. Consulte [Uso de segmentos em condições](../segment/using-a-segment.md).
* Adicione um evento **[!UICONTROL Segment qualification]** à sua jornada para ouvir as entradas e saídas dos perfis nos segmentos do Adobe Experience Platform. Consulte [Atividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de avaliação no Journey Orchestration {#evaluation-method-in-journey-orchestration}

No Journey Orchestration, os públicos-alvo são gerados a partir das definições de segmento usando um destes métodos de avaliação:

* Segmentação de transmissão - a lista de públicos-alvo do segmento é mantida atualizada em tempo real, enquanto novos dados fluem para o sistema.
* Segmentação em lote - a lista de público-alvo do segmento é atualizada de hora em hora, com base nos dados que chegaram na última hora.

A determinação entre a segmentação em lote e a segmentação por transmissão é feita pelo sistema para cada definição de segmento, com base na complexidade e no custo da avaliação da regra de segmento.

Você pode exibir o método de avaliação para cada segmento na coluna **[!UICONTROL Evaluation method]** da lista de segmentos.

Depois de definir um segmento pela primeira vez, os perfis são adicionados ao público-alvo quando se qualificam.

O preenchimento retroativo de dados anteriores no público-alvo pode levar até 24 horas. Depois que o público-alvo é preenchido retroativamente, ele será mantido atualizado continuamente e está sempre pronto para o direcionamento.