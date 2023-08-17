---
product: adobe campaign
title: Sobre segmentos da Adobe Experience Platform
description: Saiba como configurar um segmento do Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 12%

---

# Sobre segmentos da Adobe Experience Platform {#about-segments}

Se você estiver usando o [Serviço de segmentação do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=pt-BR) para criar segmentos, você pode aproveitá-los no [!DNL Journey Orchestration]. Graças a uma atividade de evento dedicada, você pode fazer com que os indivíduos entrem ou avancem em uma jornada com base nas entradas e saídas do segmento do Adobe Experience Platform. Isso também permite criar condições complexas em suas jornadas usando o editor de expressão simples ou avançado.

Digamos que você tenha um segmento de &quot;cliente prata&quot;. Com essa atividade, você pode fazer com que todos os novos clientes Silver insiram uma jornada e enviem a eles uma série de mensagens personalizadas. Você também pode criar condições facilmente com base nesse segmento.

Aqui estão as possibilidades [!DNL Journey Orchestration] oferecem segmentos:

* Acesse a lista de segmentos do Adobe Experience Platform. Consulte [Criação de um segmento](../segment/creating-a-segment.md).
* Criar segmentos diretamente no [!DNL Journey Orchestration] da mesma forma que você as cria usando o Serviço de segmentação. Consulte [Criação de um segmento](../segment/creating-a-segment.md).
* Aproveite os segmentos nas condições da sua jornada usando o editor de expressão simples ou avançado. Consulte [Uso de segmentos em condições](../segment/using-a-segment.md).
* Adicionar um **[!UICONTROL Segment qualification]** jornada para ouvir as entradas e saídas dos perfis nos segmentos do Adobe Experience Platform. Consulte [Atividades de eventos](../building-journeys/segment-qualification-events.md).

## Método de avaliação em Journey Orchestration {#evaluation-method-in-journey-orchestration}

No Journey Orchestration, os públicos-alvo são gerados a partir das definições de segmento usando um destes métodos de avaliação:

* Segmentação de transmissão - a lista de públicos-alvo do segmento é mantida atualizada em tempo real, enquanto novos dados fluem para o sistema.
* Segmentação em lote - a lista de público-alvo do segmento é atualizada de hora em hora, com base nos dados que chegaram na última hora.

A determinação entre a segmentação em lote e a segmentação por transmissão é feita pelo sistema para cada definição de segmento, com base na complexidade e no custo da avaliação da regra de segmento.

É possível exibir o método de avaliação para cada segmento na **[!UICONTROL Evaluation method]** coluna da lista de segmentos.

Depois de definir um segmento pela primeira vez, os perfis são adicionados ao público-alvo quando se qualificam.

O preenchimento retroativo de dados anteriores no público-alvo pode levar até 24 horas. Depois que o público-alvo é preenchido retroativamente, ele será mantido atualizado continuamente e está sempre pronto para o direcionamento.