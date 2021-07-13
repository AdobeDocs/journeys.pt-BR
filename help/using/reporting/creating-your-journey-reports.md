---
product: adobe campaign
title: Criação de relatórios de jornada
description: Saiba como criar relatórios do jornada
feature: Jornadas
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 5%

---

# Criação de relatórios de jornada {#concept_rfj_wpt_52b}

## Acesso e criação de relatórios {#accessing-reports}

>[!NOTE]
>
>Após excluir uma jornada, todos os relatórios associados não estarão mais disponíveis.

Esta seção apresentará como criar ou usar relatórios prontos para uso. Combine painéis, componentes e visualizações para controlar melhor o sucesso das jornadas.

Para acessar os relatórios do jornada e começar a rastrear o sucesso dos deliveries:

1. No menu superior, clique na guia **[!UICONTROL Home]**.

1. Selecione a jornada para a qual deseja criar um relatório.

   Observe que você também pode acessar seus relatórios clicando em **Report** ao passar o mouse sobre uma jornada na lista de jornadas.

   ![](../assets/dynamic_report_journey.png)

1. Clique no ícone **[!UICONTROL Report]** na parte superior direita da tela.

   ![](../assets/dynamic_report_journey_2.png)

1. O relatório pronto para uso **[!UICONTROL Journey summary]** aparece na tela. Para acessar relatórios personalizados, clique no botão **[!UICONTROL Close]**.

   ![](../assets/dynamic_report_journey_12.png)

1. Clique em **[!UICONTROL Create new project]** para criar seu relatório do zero.

   ![](../assets/dynamic_report_journey_3.png)

1. Na guia **[!UICONTROL Panels]** , arraste e solte quantos painéis ou tabelas de forma livre forem necessários. Para obter mais informações, consulte esta [seção](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Você pode começar a filtrar os dados arrastando e soltando dimensões e métricas da guia **[!UICONTROL Components]** na tabela de forma livre. Para obter mais informações, consulte esta [seção](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Para ter uma exibição mais clara dos dados, é possível adicionar visualizações da guia **[!UICONTROL Visualizations]**. Para obter mais informações, consulte esta [seção](#adding-visualizations).

## Adicionar painéis{#adding-panels}

### Adição de um painel em branco {#adding-a-blank-panel}

Para iniciar seu relatório, é possível adicionar um conjunto de painéis a um relatório pronto para uso ou personalizado. Cada painel contém conjuntos de dados diferentes e é composto de tabelas e visualizações de forma livre.

Esse painel permite que você crie seus relatórios, conforme necessário. Você pode adicionar quantos painéis desejar em seus relatórios para filtrar seus dados com períodos de tempo diferentes.

1. Clique no ícone **[!UICONTROL Panels]**. Você também pode adicionar um painel clicando em **[!UICONTROL Insert tab]** e selecionando **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arraste e solte o **[!UICONTROL Blank Panel]** no seu painel.

   ![](../assets/dynamic_report_panel.png)

Agora é possível adicionar uma tabela de forma livre ao painel para iniciar o direcionamento de dados.

### Adicionar uma tabela de forma livre {#adding-a-freeform-table}

As tabelas de forma livre permitem criar uma tabela para analisar seus dados usando as diferentes métricas e dimensões disponíveis na tabela **[!UICONTROL Component]**.

Cada tabela e visualização é redimensionável e pode ser movida para personalizar melhor seu relatório.

1. Clique no ícone **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Arraste e solte o item **[!UICONTROL Freeform]** no seu painel.

   Você também pode adicionar uma tabela clicando na guia **[!UICONTROL Insert]** e selecionando **[!UICONTROL New Freeform]** ou clicando em **[!UICONTROL Add a freeform table]** em um painel vazio.

   ![](../assets/dynamic_report_panel_2.png)

1. Arraste e solte itens da guia **[!UICONTROL Components]** nas colunas e linhas para criar a tabela.

   ![](../assets/dynamic_report_freeform_3.png)

1. Clique no ícone **[!UICONTROL Settings]** para alterar como os dados são exibidos em suas colunas.

   ![](../assets/dynamic_report_freeform_4.png)

   O **[!UICONTROL Column settings]** é composto por:

   * **[!UICONTROL Number]**: permite mostrar ou ocultar números de resumo na coluna .
   * **[!UICONTROL Percent]**: permite mostrar ou ocultar porcentagens na coluna.
   * **[!UICONTROL Interpret zero as no value]**: permite mostrar ou ocultar quando o valor é igual a zero.
   * **[!UICONTROL Background]**: permite mostrar ou ocultar a barra de progresso horizontal nas células.
   * **[!UICONTROL Include retries]**: permite incluir novas tentativas no resultado. Isso só está disponível para **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selecione uma ou várias linhas e clique no ícone **[!UICONTROL Visualize]**. Uma visualização é adicionada para refletir as linhas selecionadas.

   ![](../assets/dynamic_report_freeform_5.png)

Agora é possível adicionar quantos componentes forem necessários e também adicionar visualizações para fornecer representações gráficas de seus dados.

## Adição de componentes{#adding-components}

Os componentes ajudam você a personalizar seus relatórios com diferentes dimensões, métricas e períodos.

1. Clique na guia **[!UICONTROL Components]** para acessar a lista de componentes.

   ![](../assets/dynamic_report_components.png)

1. Cada categoria apresentada na guia **[!UICONTROL Components]** exibe os cinco itens mais usados, clique no nome de uma categoria para acessar a lista completa de componentes.

   A tabela de componentes é dividida em três categorias:

   * **[!UICONTROL Dimensions]**: Obtenha detalhes do log de deliveries, como o navegador ou domínio do recipient, ou o sucesso de um delivery.
   * **[!UICONTROL Metrics]**: Obtenha detalhes sobre o status de uma mensagem. Por exemplo, se uma mensagem foi entregue e o usuário a abriu.
   * **[!UICONTROL Time]**: Defina um período de tempo para a tabela.

1. Arraste e solte componentes em um painel para começar a filtrar os dados.

Você pode arrastar e soltar quantos componentes forem necessários e compará-los uns aos outros.

## Adicionar visualizações{#adding-visualizations}

A guia **[!UICONTROL Visualizations]** permite arrastar e soltar itens de visualização, como área, rosca e gráfico. As visualizações fornecem representações gráficas de seus dados.

1. Na guia **[!UICONTROL Visualizations]** , arraste e solte um item de visualização em um painel.

   ![](../assets/dynamic_report_visualization_1.png)

1. Após adicionar uma visualização ao painel, os relatórios detectarão automaticamente os dados na tabela de forma livre. Selecione as configurações da visualização.
1. Se você tiver mais de uma tabela de forma livre, escolha a fonte de dados disponível para adicionar em seu gráfico na janela **[!UICONTROL Data Source Settings]**. Essa janela também está disponível ao clicar no ponto colorido ao lado do título da visualização.

   ![](../assets/dynamic_report_visualization_2.png)

1. Clique no botão **[!UICONTROL Visualization]** de configurações para alterar diretamente o tipo de gráfico ou o que é exibido nele, como:

   * **[!UICONTROL Percentages]**: Exibe os valores em porcentagem.
   * **[!UICONTROL Anchor Y Axis at Zero]**: Força o eixo y a zero mesmo se os valores estiverem acima de zero.
   * **[!UICONTROL Legend visible]**: Permite ocultar a legenda.
   * **[!UICONTROL Normalization]**: Força a correspondência dos valores.
   * **[!UICONTROL Display Dual Axis]**: Adiciona outro eixo ao gráfico.
   * **[!UICONTROL Limit Max Items]**: Limita o número de gráficos exibidos.
   * **[!UICONTROL Threshold]**: Permite definir um limite para o gráfico. Aparece como uma linha pontilhada preta.

   ![](../assets/dynamic_report_visualization_3.png)

Essa visualização permite ter uma exibição mais clara dos dados nos relatórios.
