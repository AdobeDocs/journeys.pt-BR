---
product: adobe campaign
title: Criação de relatórios de jornada
description: Saiba como criar relatórios do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 5%

---

# Criação de relatórios de jornada {#concept_rfj_wpt_52b}

## Acesso e criação de relatórios {#accessing-reports}

>[!NOTE]
>
>Depois de excluir uma jornada, todos os relatórios associados não estarão mais disponíveis.

Esta seção mostrará como criar ou usar relatórios prontos para uso. Combine painéis, componentes e visualizações para melhor rastrear o sucesso de suas jornadas.

Para acessar seus relatórios de jornada e começar a rastrear o sucesso de seus deliveries:

1. No menu superior, clique na guia **[!UICONTROL Home]**.

1. Selecione a jornada sobre a qual deseja criar relatórios.

   Observe que você também pode acessar seus relatórios clicando em **Relatório** ao passar o mouse sobre uma jornada na lista de jornadas.

   ![](../assets/dynamic_report_journey.png)

1. Clique em **[!UICONTROL Report]** ícone na parte superior direita da tela.

   ![](../assets/dynamic_report_journey_2.png)

1. A variável **[!UICONTROL Journey summary]** relatório pronto para uso aparece na tela. Para acessar relatórios personalizados, clique no link **[!UICONTROL Close]** botão.

   ![](../assets/dynamic_report_journey_12.png)

1. Clique em **[!UICONTROL Create new project]** para criar seu relatório do zero.

   ![](../assets/dynamic_report_journey_3.png)

1. No **[!UICONTROL Panels]** arraste e solte quantos painéis ou tabelas de forma livre forem necessários. Para obter mais informações, consulte esta [seção](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Você pode começar a filtrar seus dados arrastando e soltando dimensões e métricas da **[!UICONTROL Components]** para a tabela de forma livre. Para obter mais informações, consulte esta [seção](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Para ter uma visualização mais clara dos dados, você pode adicionar visualizações do **[!UICONTROL Visualizations]** guia. Para obter mais informações, consulte esta [seção](#adding-visualizations).

## Adicionar painéis{#adding-panels}

### Adição de um painel em branco {#adding-a-blank-panel}

Para iniciar o relatório, é possível adicionar um conjunto de painéis a um relatório pronto para uso ou personalizado. Cada painel contém diferentes conjuntos de dados e é composto por tabelas e visualizações de forma livre.

Esse painel permite criar relatórios conforme necessário. Você pode adicionar quantos painéis desejar em seus relatórios para filtrar seus dados com diferentes períodos de tempo.

1. Clique no ícone do **[!UICONTROL Panels]**. Você também pode adicionar um painel clicando no **[!UICONTROL Insert tab]** e seleção **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arraste e solte a **[!UICONTROL Blank Panel]** no painel.

   ![](../assets/dynamic_report_panel.png)

Agora é possível adicionar uma tabela de forma livre ao painel para começar a direcionar dados.

### Adição de uma tabela de forma livre {#adding-a-freeform-table}

As tabelas de forma livre permitem criar uma tabela para analisar seus dados usando as diferentes métricas e dimensões disponíveis no **[!UICONTROL Component]** tabela.

Cada tabela e visualização é redimensionável e pode ser movida para personalizar melhor seu relatório.

1. Clique no ícone do **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arraste e solte a **[!UICONTROL Freeform]** no painel.

   Você também pode adicionar uma tabela clicando no ícone **[!UICONTROL Insert]** guia e seleção **[!UICONTROL New Freeform]** ou clicando em **[!UICONTROL Add a freeform table]** em um painel vazio.

   ![](../assets/dynamic_report_panel_2.png)

1. Arraste e solte itens da **[!UICONTROL Components]** nas colunas e linhas para criar sua tabela.

   ![](../assets/dynamic_report_freeform_3.png)

1. Clique em **[!UICONTROL Settings]** ícone para alterar como os dados são exibidos em suas colunas.

   ![](../assets/dynamic_report_freeform_4.png)

   A variável **[!UICONTROL Column settings]** é composto por:

   * **[!UICONTROL Number]**: permite mostrar ou ocultar números de resumo na coluna.
   * **[!UICONTROL Percent]**: permite mostrar ou ocultar porcentagens na coluna.
   * **[!UICONTROL Interpret zero as no value]**: permite mostrar ou ocultar quando o valor é igual a zero.
   * **[!UICONTROL Background]**: permite mostrar ou ocultar a barra de progresso horizontal em células.
   * **[!UICONTROL Include retries]**: permite incluir tentativas no resultado. Isso só está disponível para **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selecione uma ou várias linhas e clique no botão **[!UICONTROL Visualize]** ícone. Uma visualização é adicionada para refletir as linhas selecionadas.

   ![](../assets/dynamic_report_freeform_5.png)

Agora é possível adicionar quantos componentes forem necessários e também adicionar visualizações para fornecer representações gráficas de seus dados.

## Adição de componentes{#adding-components}

Os componentes ajudam você a personalizar seus relatórios com diferentes dimensões, métricas e períodos.

1. Clique em **[!UICONTROL Components]** para acessar a lista de componentes.

   ![](../assets/dynamic_report_components.png)

1. Cada categoria apresentada no **[!UICONTROL Components]** exibe os cinco itens mais usados, clique no nome de uma categoria para acessar sua lista completa de componentes.

   A tabela de componentes é dividida em três categorias:

   * **[!UICONTROL Dimensions]**: obtenha detalhes do log de deliveries, como o navegador ou domínio do recipient, ou o sucesso de um delivery.
   * **[!UICONTROL Metrics]**: obtenha detalhes sobre o status de uma mensagem. Por exemplo, se uma mensagem foi entregue e o usuário a abriu.
   * **[!UICONTROL Time]**: Defina um período para a tabela.

1. Arraste e solte componentes em um painel para começar a filtrar seus dados.

Você pode arrastar e soltar quantos componentes forem necessários e compará-los entre si.

## Adicionar visualizações{#adding-visualizations}

A variável **[!UICONTROL Visualizations]** permite arrastar e soltar itens de visualização, como área, rosca e gráfico. As visualizações fornecem representações gráficas de seus dados.

1. No **[!UICONTROL Visualizations]** arraste e solte um item de visualização em um painel.

   ![](../assets/dynamic_report_visualization_1.png)

1. Depois de adicionar uma visualização ao painel, os relatórios detectarão automaticamente os dados na tabela de forma livre. Selecione as configurações da visualização.
1. Se você tiver mais de uma tabela de forma livre, escolha a fonte de dados disponível para adicionar ao seu gráfico na **[!UICONTROL Data Source Settings]** janela. Essa janela também está disponível clicando no ponto colorido ao lado do título da visualização.

   ![](../assets/dynamic_report_visualization_2.png)

1. Clique em **[!UICONTROL Visualization]** botão de configurações para alterar diretamente o tipo de gráfico ou o que é exibido nele, como:

   * **[!UICONTROL Percentages]**: exibe os valores em porcentagem.
   * **[!UICONTROL Anchor Y Axis at Zero]**: força o eixo y a zero, mesmo se os valores estiverem acima de zero.
   * **[!UICONTROL Legend visible]**: permite ocultar a legenda.
   * **[!UICONTROL Normalization]**: força os valores a serem correspondentes.
   * **[!UICONTROL Display Dual Axis]**: adiciona outro eixo ao gráfico.
   * **[!UICONTROL Limit Max Items]**: limita o número de gráficos exibidos.
   * **[!UICONTROL Threshold]**: permite definir um limite para o gráfico. Aparece como uma linha pontilhada preta.

   ![](../assets/dynamic_report_visualization_3.png)

Essa visualização permite que você tenha uma visualização mais clara dos dados em seus relatórios.
