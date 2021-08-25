---
product: adobe campaign
title: Sobre segmentos do Adobe Experience Platform
description: Saiba como configurar um segmento do Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# Sobre segmentos do Adobe Experience Platform {#about-segments}

Se estiver usando o [Serviço de segmentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) para criar seus segmentos, você pode aproveitá-los em [!DNL Journey Orchestration]. Graças a uma atividade dedicada de evento, você pode fazer indivíduos entrarem ou avançarem em uma jornada com base nas entradas e saídas do segmento do Adobe Experience Platform. Isso também permite criar condições complexas em suas jornadas usando o editor de expressão simples ou avançado.

Digamos que você tenha um segmento de &quot;cliente prateado&quot;. Com essa atividade, você pode fazer com que todos os novos clientes de prata insiram uma jornada e enviem uma série de mensagens personalizadas. Você também pode criar condições facilmente com base nesse segmento.

Estas são as possibilidades [!DNL Journey Orchestration] oferecidas com segmentos:

* Acesse a lista de segmentos do Adobe Experience Platform. Consulte [Criação de um segmento](../segment/creating-a-segment.md).
* Crie segmentos diretamente em [!DNL Journey Orchestration] da mesma forma que os cria usando o Serviço de segmentação. Consulte [Criação de um segmento](../segment/creating-a-segment.md).
* Aproveite os segmentos das condições da jornada usando o editor de expressão simples ou avançado. Consulte [Uso de segmentos em condições](../segment/using-a-segment.md).
* Adicione um evento **[!UICONTROL Segment qualification]** à jornada para ouvir as entradas e saídas dos perfis nos segmentos do Adobe Experience Platform. Consulte [Atividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de avaliação em Journey Orchestration {#evaluation-method-in-journey-orchestration}

No Journey Orchestration, os públicos-alvo são gerados a partir das definições de segmento usando um destes métodos de avaliação:

* Segmentação de fluxo - a lista de públicos-alvo do segmento é mantida atualizada em tempo real, enquanto novos dados fluem para o sistema.
* Segmentação em lote - a lista de públicos-alvo do segmento é atualizada de hora em hora, com base nos dados que chegaram na última hora.

A determinação entre a segmentação de lote e a segmentação de fluxo é feita pelo sistema para cada definição de segmento, com base na complexidade e no custo da avaliação da regra de segmento.

Você pode exibir o método de avaliação para cada segmento na coluna **[!UICONTROL Evaluation method]** da lista de segmentos.

Após ter definido um segmento pela primeira vez, os perfis são adicionados ao público-alvo quando se qualificam.

O preenchimento retroativo do público-alvo a partir de dados anteriores pode demorar até 24 horas. Após o preenchimento retroativo do público-alvo, ele é continuamente atualizado e está sempre pronto para o direcionamento.