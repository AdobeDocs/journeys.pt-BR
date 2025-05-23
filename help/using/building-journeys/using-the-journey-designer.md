---
product: adobe campaign
title: Usar o designer de jornada
description: Saiba mais sobre como usar o designer do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 2f001e42-46dd-48aa-b3dd-23bfdf97e1c7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---

# Usar o designer de jornada {#concept_m1g_5qt_52b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


O menu Página Inicial do jornada permite exibir a **lista de jornadas**. Crie uma nova jornada ou clique em uma existente para abrir a **interface do designer de jornadas**. O designer é composto das seguintes zonas: a paleta, a tela e o painel de configuração da atividade.

## A lista de jornadas {#journey_list}

A **lista de jornadas** permite exibir todas as jornadas de uma só vez, ver o status e executar ações básicas. Você pode duplicar, interromper ou excluir suas jornadas. Dependendo da jornada, certas ações podem não estar disponíveis. Por exemplo, você não pode excluir ou reiniciar uma jornada encerrada. Você pode criar uma nova versão a partir dela, duplicá-la ou interrompê-la. Você também pode usar a barra de pesquisa para procurar uma jornada.

Os **[!UICONTROL Filters]** podem ser acessados com um clique no ícone de filtro na parte superior esquerda da lista. O menu de filtros permite filtrar as jornadas exibidas de acordo com diferentes critérios (status, aqueles que você criou, aqueles modificados nos últimos 30 dias, somente as versões mais recentes etc.). Você também pode optar por exibir somente as jornadas que usam um evento, grupo de campos ou ação específica. As colunas exibidas na lista podem ser configuradas. Todos os filtros e colunas são salvos por usuário.

![](../assets/journey74.png)

Todas as versões das jornadas são exibidas na lista com o número da versão. Consulte [esta página](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Para abrir a tela de uma jornada em outra guia do navegador, mantenha pressionada a tecla **Control** ou **Command** e clique na jornada.

## A paleta {#palette}

A **paleta** está no lado esquerdo da tela. Todas as atividades disponíveis estão classificadas em várias categorias: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** e **[!UICONTROL Actions]**. Você pode expandir/recolher as diferentes categorias clicando no nome delas. Para usar uma atividade na jornada, arraste-a e solte-a da paleta na tela. Você também pode clicar duas vezes em uma atividade na paleta para adicioná-la à tela na próxima etapa disponível. É necessário configurar cada atividade adicionada da paleta antes de publicar a jornada. Se você soltar uma atividade na tela e não concluir a configuração, ela permanecerá na tela, mas um aviso vermelho indicará que a configuração não foi concluída para essa atividade.

>[!NOTE]
>
>Observe que há regras ao configurar uma jornada. A configuração não permitida será descartada. Por exemplo, não é possível colocar ações em paralelo, vincular uma atividade a uma etapa anterior para criar um loop, iniciar uma jornada com algo diferente de um evento etc.

![](../assets/journey38.png)

O ícone **[!UICONTROL Filter items]** no canto superior esquerdo permite exibir os seguintes filtros:

* **Mostrar apenas itens disponíveis**: ocultar ou exibir elementos indisponíveis na paleta, por exemplo, os eventos que usam um namespace diferente daqueles usados em sua jornada. Por padrão, os itens indisponíveis ficam ocultos. Se você optar por exibi-los, eles aparecerão esmaecidos.

* **Mostrar apenas itens recentes**: este filtro permite exibir apenas os cinco últimos eventos e ações usados, além dos prontos para uso. Isso é específico para cada usuário. Por padrão, todos os itens são exibidos.

![](../assets/palette-filter.png)

Você também pode usar o campo **[!UICONTROL Search]**. Somente eventos e ações são filtrados.

## A tela {#canvas}

A **tela** é a zona central no designer de jornada. É nessa zona que você pode descartar suas atividades e configurá-las. Clique em uma atividade na tela para configurá-la. Isso abre o painel de configuração de atividade no lado direito. É possível aumentar e diminuir o zoom usando os botões &quot;+&quot; e &quot;-&quot; no canto superior direito. Na tela, todas as atividades permitem adicionar uma próxima etapa após elas, exceto **[!UICONTROL End]** atividades (consulte [esta página](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## O painel de configuração da atividade {#configuration_pane}

O **painel de configuração da atividade** aparece quando você clica em uma atividade na paleta. Preencha os campos obrigatórios. Clique no ícone **[!UICONTROL Delete]** para excluir a atividade. Clique em **[!UICONTROL Cancel]** para cancelar as modificações ou em **[!UICONTROL Ok]** para confirmar. Para excluir atividades, você também pode selecionar uma (ou várias) atividades e pressionar a tecla backspace. Pressionar a tecla Escape fechará o painel de configuração da atividade.

Na tela, suas atividades de ação e evento são representadas por um ícone com o nome do evento ou ação exibido abaixo. No painel de configuração da atividade, é possível usar o campo **[!UICONTROL Label]** para adicionar um sufixo ao nome da atividade. Esses rótulos ajudarão você a contextualizar o uso de eventos e ações, especialmente quando você usa o mesmo evento ou ação várias vezes na jornada. Você também poderá ver os rótulos adicionados nos relatórios do [!DNL Journey Orchestration]. Você também pode definir rótulos para suas atividades de condição.

Por padrão, os campos somente leitura ficam ocultos. Para mostrar campos somente leitura, clique no ícone **Mostrar campos somente leitura** na parte superior esquerda do painel de configuração da atividade. Essa configuração se aplica a todas as atividades em todas as jornadas.

![](../assets/journey59bis.png)

## As ações da barra superior {#top_actions}

Dependendo do status da jornada, você pode executar ações diferentes na jornada usando os botões disponíveis no canto superior direito: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Esses botões aparecem quando nenhuma atividade é selecionada. Alguns botões serão exibidos de forma contextual. O botão de log do modo de teste aparece quando o modo de teste é ativado (consulte [esta página](../building-journeys/testing-the-journey.md)). O botão de relatório é exibido quando a jornada está ativa, parada ou fechada.

![](../assets/journey41.png)

## O uso de caminhos na tela {#paths}

Várias atividades (**[!UICONTROL Condition]**, **[!UICONTROL Action]** atividades) permitem definir uma ação de fallback em caso de erro ou tempo limite. No painel de configuração da atividade, marque a caixa: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Outro caminho é adicionado após a atividade. A duração do tempo limite é definida nas propriedades da jornada (consulte [esta página](../building-journeys/changing-properties.md) por um usuário administrador. Por exemplo, se um email demorar muito para ser enviado ou estiver com erro, você pode decidir enviar um SMS.

![](../assets/journey42.png)

Várias atividades (evento, ação, espera) permitem adicionar vários caminhos após elas. Para fazer isso, coloque o cursor na atividade e clique no símbolo &quot;+&quot;. Somente atividades de evento e espera podem ser definidas em paralelo. Se vários eventos forem definidos em paralelo, o caminho escolhido será o do primeiro evento que ocorrer.

Ao ouvir um evento, recomendamos que você não espere o evento indefinidamente. Não é obrigatório, apenas uma prática recomendada. Se quiser ouvir um ou vários eventos somente durante um determinado tempo, coloque um ou vários eventos e uma atividade de espera em paralelo. Consulte [esta seção](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Para excluir o caminho, coloque o cursor sobre ele e clique no ícone **[!UICONTROL Delete arrow]**.

![](../assets/journey42ter.png)

Na tela, quando duas atividades são desconectadas, um aviso é exibido. Coloque o cursor no ícone de aviso para exibir a mensagem de erro. Para corrigir o problema, basta mover a atividade desconectada e conectá-la à atividade anterior.

![](../assets/canvas-disconnected.png)

## Atividades de cópia e colagem {#copy-paste}

É possível copiar uma ou várias atividades de uma jornada e colá-las na mesma jornada ou em uma diferente. Isso permite economizar tempo se você quiser reutilizar várias atividades que já foram configuradas em uma jornada anterior.

**Observações importantes**

* Você pode copiar/colar em diferentes guias e navegadores. Você só pode copiar/colar atividades dentro da mesma instância.
* Não é possível copiar/colar um evento se a jornada de destino tiver um evento que use um namespace diferente.
* As atividades coladas podem fazer referência a dados que não existem na jornada de destino, por exemplo, se você copiar/colar em diferentes sandboxes. Sempre verifique se há erros e faça os ajustes necessários.
* Observe que não é possível desfazer uma ação. Para excluir atividades coladas, será necessário selecioná-las e excluí-las. Portanto, selecione apenas as atividades necessárias antes de copiá-las.
* É possível copiar atividades de qualquer jornada, mesmo aquelas que estão em modo somente leitura.
* Você pode selecionar qualquer atividade, mesmo aquelas que não estão vinculadas. As atividades vinculadas permanecerão vinculadas após serem coladas.

Estas são as etapas para copiar/colar atividades:

1. Abra uma jornada.
1. Selecione as atividades que deseja copiar movendo o mouse enquanto clica. Você também pode clicar em cada atividade enquanto pressiona a tecla **Ctrl/Command**. Use **Ctrl/Command + A** se desejar selecionar todas as atividades.
   ![](../assets/copy-paste1.png)
1. Pressione **Ctrl/Command + C**.
Se quiser copiar apenas uma atividade, clique nela e use o ícone **Copiar** na parte superior esquerda do painel de configuração da atividade.
   ![](../assets/copy-paste2.png)
1. Em qualquer jornada, pressione **Ctrl/Command + V** para colar as atividades sem vinculá-las a um nó existente. As atividades coladas são colocadas na mesma ordem. Depois de coladas, as atividades permanecem selecionadas para que você possa movê-las facilmente. Você também pode colocar o cursor em um espaço reservado vazio e pressionar **Ctrl/Command + V**. As atividades coladas serão vinculadas ao nó.
   ![](../assets/copy-paste3.png)
