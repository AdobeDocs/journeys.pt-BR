---
product: adobe campaign
solution: Journey Orchestration
title: Sobre a construção de jornada
description: Como usuário empresarial, aprenda a combinar atividades de evento, orquestração e ação para criar uma jornada.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---



# Criar uma jornada {#concept_gq5_sqt_52b}

This step is performed by the **business user**. Aqui é onde você cria suas viagens. Combine diferentes atividades de evento, orquestração e ação para criar cenários de canais em várias etapas.

A interface de jornada permite que você arraste e solte facilmente atividades da paleta para a tela. Você também pode clicar com o duplo em uma atividade para adicioná-la à tela na próxima etapa disponível. Cada atividade tem um papel e um lugar específicos no processo. As atividades são sequenciadas. Quando uma atividade é concluída, o fluxo continua e processa a próxima atividade e assim por diante.

Apenas uma namespace é permitida por viagem. Quando você solta a primeira evento, eventos com namespaces diferentes ficam esmaecidos. Se o primeiro evento não tiver uma namespace, então todos os eventos com uma namespace estarão esmaecidos. Consulte [esta página](../event/selecting-the-namespace.md). Além disso, grupos de campo da Adobe Experience Platform ficam esmaecidos se a jornada tiver eventos sem namespace. E finalmente, se você usar vários eventos na mesma jornada, eles precisam usar a mesma namespace.

## Quick start {#creating_journey}

Estes são os principais passos para criar e publicar uma jornada.

1. No menu superior, clique na guia **[!UICONTROL Home]**.

   A lista das viagens é exibida. Refer to [this page](../building-journeys/using-the-journey-designer.md) for more information on the interface.

   ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

   ![](../assets/journey31.png)

1. Edite as propriedades da jornada no painel de configuração exibido no lado direito. Consulte [esta página](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Start arrastando e soltando uma atividade de evento da paleta na tela. Você também pode clicar com o duplo em uma atividade para adicioná-la à tela de desenho.

   ![](../assets/journey33.png)

1. Arraste e solte suas outras atividades e configure-as. Consulte as páginas atividades [do](../building-journeys/event-activities.md)Evento, [Sobre atividades](../building-journeys/about-orchestration-activities.md) de orquestração e [Sobre atividades](../building-journeys/about-action-activities.md)de ação.

   ![](../assets/journey34.png)

1. Sua jornada é automaticamente salva. Teste sua jornada e publique-a. Consulte [Testando a jornada](../building-journeys/testing-the-journey.md) e [Publicando a jornada](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminar uma viagem {#ending_a_journey}

Há duas maneiras de terminar uma jornada:

* A pessoa chega na última atividade de um caminho. Esta última atividade pode ser uma atividade final ou outra atividade. Não há obrigação de terminar um caminho com uma atividade final. Consulte [esta página](../building-journeys/end-activity.md).
* A pessoa chega a uma atividade de condição (ou uma atividade de espera com uma condição) e não corresponde a nenhuma das condições.

A pessoa pode então voltar a entrar na viagem se a reentrada for permitida. Consulte [esta página](../building-journeys/changing-properties.md).
