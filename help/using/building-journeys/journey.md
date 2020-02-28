---
title: Sobre construção de viagens
description: Aprenda como construir uma jornada
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec

---



# Criação de uma jornada {#concept_gq5_sqt_52b}

Esta etapa é executada pelo usuário **da** empresa. Aqui é onde você cria suas viagens. Combine as diferentes atividades de evento, orquestração e ação para criar seus cenários multicanal.

A interface de jornada permite que você arraste e solte facilmente atividades da paleta na tela. Você também pode clicar duas vezes em uma atividade para adicioná-la à tela na próxima etapa disponível. Cada atividade tem uma função e um lugar específicos no processo. As atividades são sequenciadas. Quando uma atividade é concluída, o fluxo continua e processa a próxima atividade e assim por diante.

Somente um namespace é permitido por jornada. Quando você solta o primeiro evento, os eventos com namespaces diferentes ficam esmaecidos. Se o primeiro evento não tiver um namespace, todos os eventos com um namespace estarão esmaecidos. Consulte [](../event/selecting-the-namespace.md). Além disso, os grupos de campos da Plataforma de experiência ficam esmaecidos se a jornada tiver eventos sem um namespace. E finalmente, se você usar vários eventos na mesma jornada, eles precisam usar o mesmo namespace.

## Quick start {#creating_journey}

Estes são os principais passos para criar e publicar uma jornada.

1. No menu superior, clique na **[!UICONTROL Home]** guia.

   A lista de viagens é exibida. Consulte [](../building-journeys/using-the-journey-designer.md) para obter mais informações sobre a interface.

   ![](../assets/journey30.png)

1. Clique **[!UICONTROL Create]** para criar uma nova jornada.

   ![](../assets/journey31.png)

1. Edite as propriedades da jornada no painel de configuração exibido no lado direito. Consulte [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Comece arrastando e soltando uma atividade de evento da paleta na tela. Você também pode clicar duas vezes em uma atividade para adicioná-la à tela de desenho.

   ![](../assets/journey33.png)

1. Arraste e solte suas outras atividades e configure-as. See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Sua jornada é automaticamente salva. Teste sua jornada e publique-a. Consulte [](../building-journeys/testing-the-journey.md) e [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminar uma viagem {#ending_a_journey}

Há duas maneiras de terminar uma jornada:

* A pessoa chega na última atividade de um caminho. Esta última atividade pode ser uma atividade final ou outra atividade. Não há obrigação de encerrar um caminho com uma atividade final. Consulte [](../building-journeys/end-activity.md).
* A pessoa chega a uma atividade de condição (ou uma atividade de espera com uma condição) e não corresponde a nenhuma das condições.

A pessoa pode então voltar a entrar na viagem se a reentrada for permitida. Consulte [](../building-journeys/changing-properties.md).
