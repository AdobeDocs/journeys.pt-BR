---
title: Sobre relatórios de jornada
description: Saiba como criar seus relatórios de jornada
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---


# Sobre relatórios de jornada {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Os dados do delivery e o componente Segmentos só serão preenchidos se você tiver o Adobe Campaign Standard.

Esta seção apresentará como acessar e usar relatórios para medir a eficácia de suas viagens.

## Interface de relatórios {#reporting-interface}

A barra de ferramentas superior permite, por exemplo, modificar, salvar ou imprimir seu relatório.

![](../assets/dynamic_report_toolbar.png)

Use a **[!UICONTROL Project]** guia para:

* **[!UICONTROL Open]**: abre um relatório ou modelo criado anteriormente.
* **[!UICONTROL Save As]**: Modelos de duplicados para poder modificá-los.
* **[!UICONTROL Refresh project]**: atualiza seu relatório com base em novos dados e alterações nos filtros.
* **[!UICONTROL Download CSV]**: exporta seus relatórios para um arquivo CSV.
* **[!UICONTROL Print]**: imprime seu relatório.

A **[!UICONTROL Edit]** guia permite:

* **[!UICONTROL Undo]**: cancela sua última ação em seu painel.
* **[!UICONTROL Redo]**: cancela sua última **[!UICONTROL Undo]** ação no seu painel.
* **[!UICONTROL Clear all]**: exclui todos os painéis do seu painel.

A **[!UICONTROL Insert]** tabela permite personalizar seus relatórios adicionando gráficos e tabelas ao seu painel:

* **[!UICONTROL New Blank Panel]**: adiciona um novo painel em branco ao seu painel.
* **[!UICONTROL New Freeform]**: adiciona uma nova tabela de forma livre ao seu painel.
* **[!UICONTROL New Line]**: adiciona um novo gráfico de linhas ao seu painel.
* **[!UICONTROL New Bar]**: adiciona um novo gráfico de barras ao seu painel.

As guias à esquerda permitem que você crie seu relatório e filtre seus dados conforme necessário.

![](../assets/dynamic_report_interface.png)

Essas guias fornecem acesso aos seguintes itens:

* **[!UICONTROL Panels]**: adicione um painel em branco ou forma livre ao seu relatório para filtrar seus dados por start. For more on this, refer to the [Adding panels](../reporting/creating-your-journey-reports.md#adding-panels) section
* **[!UICONTROL Visualizations]**: arraste e solte uma seleção de itens de visualização para dar ao seu relatório uma dimensão gráfica. For more on this, refer to the [Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations) section.
* **[!UICONTROL Components]**: personalize seus relatórios com diferentes dimensões, métricas, segmentos e períodos. For more on this, refer to the [Adding components](../reporting/creating-your-journey-reports.md#adding-components) section.

## Modelo de resumo de viagem {#ootb-template}

Os relatórios são divididos em duas categorias: um modelo predefinido e relatórios personalizados.
O modelo predefinido, **[!UICONTROL Journey summary]**, fornece uma visualização clara dos dados de rastreamento mais importantes.

![](../assets/dynamic_report_journey_8.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar a forma como os detalhes são exibidos em suas respectivas configurações de visualização.

Os seguintes KPIs estão disponíveis na parte superior do relatório:

* **[!UICONTROL Journey - Entered]**: número total de pessoas que chegaram ao evento de entrada da viagem.
* **[!UICONTROL Journey - Completion rate]**: número total de pessoas que chegaram ao fim da viagem (ou, no caso de uma pessoa que não corresponde a nenhuma condição) em comparação com o número total de pessoas que entraram na viagem.
* **[!UICONTROL Journey - Current]**: número total de indivíduos que se encontram atualmente na viagem.
* **[!UICONTROL Journey - Failed rate]**: número total de viagens que não foram executadas com êxito em comparação com o número de viagens em curso.
* **[!UICONTROL Delivery - Messages sent]**: número total de mensagens enviadas.
* **[!UICONTROL Delivery rate]**: número total de mensagens entregues com êxito em comparação com as mensagens enviadas.
* **[!UICONTROL Delivery - Bounce rate]**: o número total de mensagens que retornaram em comparação com as mensagens enviadas.
* **[!UICONTROL Delivery - Unsubscribed rate]**: número total de unsubscription por recipient em comparação às mensagens entregues.
* **[!UICONTROL Delivery - Open rate]**: número total de mensagens abertas em comparação ao número de mensagens entregues.
* **[!UICONTROL Delivery - Click rate]**: número total de cliques em um delivery em comparação ao número de mensagens entregues.

A visualização do fluxo de jornada permite que você veja o caminho dos perfis direcionados passo a passo em sua jornada. Isso só está disponível quando se trata de uma jornada. É gerado automaticamente e não pode ser modificado.

![](../assets/dynamic_report_journey_10.png)

A **[!UICONTROL Journey summary]** tabela contém os dados disponíveis para sua jornada, como:

* **[!UICONTROL Entered]**: número total de pessoas que chegaram ao evento de entrada da viagem.
* **[!UICONTROL Completion rate]**: número total de indivíduos que atingiram o controlo de fluxo final da viagem em comparação com o número total de indivíduos que entraram na viagem.
* **[!UICONTROL Current]**: número total de indivíduos que se encontram atualmente na viagem.
* **[!UICONTROL Failed]**: número total de viagens que não foram executadas com êxito.
* **[!UICONTROL Failed rate]**: número total de viagens que não foram executadas com êxito em comparação com o número de viagens em curso.

A **[!UICONTROL Top events]** tabela exibe os eventos mais bem-sucedidos e **[!UICONTROL Top action]** as ações mais bem-sucedidas em suas viagens.

![](../assets/dynamic_report_journey_11.png)

A **[!UICONTROL Delivery - Sending summary]** tabela contém os dados disponíveis para os delivery de sua jornada, como:

* **[!UICONTROL Processed/sent]**: número total de mensagens enviadas.
* **[!UICONTROL Delivered rate]**: número total de mensagens entregues com êxito em comparação com as mensagens enviadas.
* **[!UICONTROL Delivered]**: número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas.
* **[!UICONTROL Bounce + error rate]**: o número total de mensagens que retornaram em comparação com as mensagens enviadas.
* **[!UICONTROL Bounces + errors]**: Total de erros acumulados durante o processamento de retorno automático e delivery em relação ao número total de mensagens enviadas.

A **[!UICONTROL Delivery - Tracking summary]** tabela contém os dados disponíveis para rastrear o sucesso dos delivery de suas viagens, como:

* **[!UICONTROL Open Rate]**: porcentagem de mensagens abertas.
* **[!UICONTROL Open]**: número de vezes que uma mensagem foi aberta em um delivery.
* **[!UICONTROL Click trough rate]**: número total de cliques em um delivery em comparação ao número de mensagens entregues.
* **[!UICONTROL Click]**: número de vezes que um conteúdo foi clicado em um delivery.
* **[!UICONTROL Unsubscribe rate]**: porcentagem de unsubscription por recipient em relação às mensagens entregues.
* **[!UICONTROL Unsubscribed]**: número total de unsubscription por recipient em comparação às mensagens entregues.
