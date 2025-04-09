---
product: adobe campaign
title: Sobre relatórios de jornada
description: Saiba como criar relatórios do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Sobre relatórios de jornada {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._



>[!NOTE]
>
>O componente de Dados de entrega e Segmentos só será preenchido se você tiver o Adobe Campaign Standard.

Esta seção mostrará como acessar e usar os relatórios para medir a eficiência da sua jornada.

## Interface de relatórios {#reporting-interface}

A barra de ferramentas superior permite, por exemplo, modificar, salvar ou imprimir o relatório.

![](../assets/dynamic_report_toolbar.png)

Use a guia **[!UICONTROL Project]** para:

* **[!UICONTROL Open]**: abre um relatório ou modelo criado anteriormente.
* **[!UICONTROL Save As]**: duplica modelos para poder modificá-los.
* **[!UICONTROL Refresh project]**: atualiza seu relatório com base em novos dados e alterações em filtros.
* **[!UICONTROL Download CSV]**: exporta seus relatórios para um arquivo CSV.
* **[!UICONTROL Print]**: imprime seu relatório.

A guia **[!UICONTROL Edit]** permite:

* **[!UICONTROL Undo]**: cancela sua última ação no painel.
* **[!UICONTROL Redo]**: cancela sua última ação de **[!UICONTROL Undo]** no painel.
* **[!UICONTROL Clear all]**: exclui cada painel em seu painel.

A tabela **[!UICONTROL Insert]** permite personalizar seus relatórios adicionando gráficos e tabelas ao painel:

* **[!UICONTROL New Blank Panel]**: adiciona um novo painel em branco ao painel.
* **[!UICONTROL New Freeform]**: adiciona uma nova tabela de forma livre ao painel.
* **[!UICONTROL New Line]**: adiciona um novo gráfico de linhas ao seu painel.
* **[!UICONTROL New Bar]**: adiciona um novo gráfico de barras ao painel.

As guias à esquerda permitem criar o relatório e filtrar os dados conforme necessário.

![](../assets/dynamic_report_interface.png)

Essas guias fornecem acesso aos seguintes itens:

* **[!UICONTROL Panels]**: adicione um painel ou formato livre em branco ao relatório para começar a filtrar seus dados. Para obter mais informações, consulte a seção [Adicionando painéis](../reporting/creating-your-journey-reports.md#adding-panels)
* **[!UICONTROL Visualizations]**: arraste e solte uma seleção de itens de visualização para dar ao seu relatório uma dimensão gráfica. Para obter mais informações, consulte a seção [Adição de visualizações](../reporting/creating-your-journey-reports.md#adding-visualizations).
* **[!UICONTROL Components]**: personalize seus relatórios com diferentes dimensões, métricas, segmentos e períodos. Para obter mais informações, consulte a seção [Adicionando componentes](../reporting/creating-your-journey-reports.md#adding-components).

## Jornada modelo de resumo {#ootb-template}

Os relatórios são divididos em duas categorias: um modelo pronto para uso e relatórios personalizados.
O modelo pronto para uso, **[!UICONTROL Journey summary]**, fornece uma visão clara dos dados de rastreamento mais importantes.

![](../assets/dynamic_report_journey_8.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

Os seguintes KPIs estão disponíveis na parte superior do relatório:

* **[!UICONTROL Journey - Entered]**: número total de pessoas físicas que atingiram o evento de entrada da jornada.
* **[!UICONTROL Journey - Completion rate]**: número total de indivíduos que atingiram o fim da jornada (ou, no caso de um indivíduo que não corresponde a nenhuma condição) em comparação ao número total de indivíduos que entraram na jornada.
* **[!UICONTROL Journey - Current]**: número total de indivíduos atualmente na jornada.
* **[!UICONTROL Journey - Failed rate]**: número total de jornadas que não foram executadas com êxito em comparação ao número de jornadas executadas.
* **[!UICONTROL Delivery - Messages sent]**: número total de mensagens enviadas.
* **[!UICONTROL Delivery rate]**: número total de mensagens entregues com êxito em comparação às mensagens enviadas.
* **[!UICONTROL Delivery - Bounce rate]**: número total de mensagens que foram rejeitadas em comparação às mensagens enviadas.
* **[!UICONTROL Delivery - Unsubscribed rate]**: número total de cancelamentos de assinatura por recipient em comparação às mensagens entregues.
* **[!UICONTROL Delivery - Open rate]**: número total de mensagens abertas em comparação ao número de mensagens entregues.
* **[!UICONTROL Delivery - Click rate]**: número total de cliques em uma entrega em comparação ao número de mensagens entregues.

A visualização do fluxo de Jornada permite que você veja o caminho dos perfis direcionados passo a passo pela jornada. Isso só está disponível para direcionar uma jornada. Ele é gerado automaticamente e não pode ser modificado.

![](../assets/dynamic_report_journey_10.png)

A tabela **[!UICONTROL Journey summary]** contém os dados disponíveis para sua jornada, como:

* **[!UICONTROL Entered]**: número total de pessoas físicas que atingiram o evento de entrada da jornada.
* **[!UICONTROL Completion rate]**: número total de indivíduos que atingiram o controle de fluxo final da jornada em comparação ao número total de indivíduos que entraram na jornada.
* **[!UICONTROL Current]**: número total de indivíduos atualmente na jornada.
* **[!UICONTROL Failed]**: número total de jornadas que não foram executadas com êxito.
* **[!UICONTROL Failed rate]**: número total de jornadas que não foram executadas com êxito em comparação ao número de jornadas executadas.

A tabela **[!UICONTROL Top events]** exibe os eventos mais bem-sucedidos e a **[!UICONTROL Top action]**, as ações mais bem-sucedidas em suas jornadas.

![](../assets/dynamic_report_journey_11.png)

A tabela **[!UICONTROL Delivery - Sending summary]** contém os dados disponíveis para as entregas de sua jornada, como:

* **[!UICONTROL Processed/sent]**: número total de mensagens enviadas.
* **[!UICONTROL Delivered rate]**: número total de mensagens entregues com êxito em comparação às mensagens enviadas.
* **[!UICONTROL Delivered]**: número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas.
* **[!UICONTROL Bounce + error rate]**: número total de mensagens que foram rejeitadas em comparação às mensagens enviadas.
* **[!UICONTROL Bounces + errors]**: total de erros acumulados durante o processamento de entrega e retorno automático em relação ao número total de mensagens enviadas.

A tabela **[!UICONTROL Delivery - Tracking summary]** contém os dados disponíveis para acompanhar o sucesso das entregas de suas jornadas, como:

* **[!UICONTROL Open Rate]**: porcentagem de mensagens abertas.
* **[!UICONTROL Open]**: número de vezes que uma mensagem foi aberta em uma entrega.
* **[!UICONTROL Click trough rate]**: número total de cliques em uma entrega em comparação ao número de mensagens entregues.
* **[!UICONTROL Click]**: número de vezes que um conteúdo foi clicado em uma entrega.
* **[!UICONTROL Unsubscribe rate]**: porcentagem de cancelamentos de assinatura por destinatário em comparação às mensagens entregues.
* **[!UICONTROL Unsubscribed]**: número total de cancelamentos de assinatura por recipient em comparação às mensagens entregues.
