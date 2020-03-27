---
title: Usar o designer de jornada
description: Saiba mais sobre como usar o designer de jornada
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
source-git-commit: 18f5d56e77958fc33c8e5e7e9d450943207a6017

---


# Usar o designer de jornada {#concept_m1g_5qt_52b}

O menu Início da jornada permite que você visualização a **lista das viagens**. Crie uma nova jornada ou clique em uma já existente para abrir a interface **do designer de** jornada. O criador é constituído pelas seguintes zonas: a paleta, a tela e o painel de configuração da atividade.

## A lista da viagem {#journey_list}

>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;Sobre a lista da jornada&quot;
>abstract=&quot;A lista de viagem permite que você visualização todas as suas viagens de uma só vez, veja seu status e execute ações básicas. Você pode duplicado, parar ou excluir suas viagens. Dependendo da jornada, certas ações podem não estar disponíveis. Por exemplo, você não pode excluir ou reiniciar uma jornada que esteja concluída. Você pode criar uma nova versão ou duplicado-a. Você também pode usar a barra de pesquisa para procurar uma jornada.&quot;
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Assista ao vídeo de demonstração&quot;

A lista **de** viagem permite visualização de todas as suas viagens de uma só vez, ver seu status e realizar ações básicas. Você pode duplicado, parar ou excluir suas viagens. Dependendo da jornada, certas ações podem não estar disponíveis. Por exemplo, você não pode excluir ou reiniciar uma jornada que esteja concluída. Você pode criar uma nova versão ou duplicado-a. Você também pode usar a barra de pesquisa para procurar uma jornada.

Para **[!UICONTROL Filters]** acessá-lo, clique no ícone de filtro na parte superior esquerda da lista. O menu filtros permite que você filtre as viagens exibidas de acordo com critérios diferentes (status, aqueles criados, os modificados nos últimos 30 dias, somente as versões mais recentes etc.). Você também pode optar por exibir somente as viagens que usam um evento, grupo de campos ou ação específicos. As colunas exibidas na lista podem ser configuradas. Todos os filtros e colunas são salvos por usuário.

![](../assets/journey74.png)

Todas as versões de suas viagens aparecem na lista com o número da versão. Consulte [](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Para abrir a tela de uma jornada em uma guia diferente do navegador, mantenha pressionada a tecla **Control** ou **Command** e clique na jornada.

## A paleta {#palette}

A **paleta** fica do lado esquerdo da tela. Todas as atividades disponíveis são classificadas em várias categorias: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** e **[!UICONTROL Actions]**. Você pode expandir/recolher as diferentes categorias clicando em seu nome. Para usar uma atividade em sua jornada, arraste-a e solte-a da paleta até sua tela. Você também pode clicar com o duplo em uma atividade na paleta para adicioná-la à tela de desenho, na próxima etapa disponível. É necessário configurar cada atividade adicionada a partir da paleta antes de publicar a jornada. Se você soltar uma atividade na tela e não terminar sua configuração, ela permanecerá na tela, mas um aviso vermelho indicará que a configuração não foi concluída para essa atividade.

>[!NOTE]
>
>Observe que existem regras ao configurar uma jornada. A configuração não permitida será descartada. Por exemplo, não é possível colocar ações em paralelo, vincular uma atividade a uma etapa anterior para criar um loop, start uma jornada com algo diferente de um evento etc.

![](../assets/journey38.png)

O ícone **Mostrar itens** desativados no canto superior esquerdo permite ocultar ou exibir elementos indisponíveis na paleta, por exemplo, os eventos que usam uma namespace diferente daqueles usados em sua jornada. Por padrão, os itens indisponíveis ficam ocultos. Se você optar por exibi-los, eles aparecerão esmaecidos.

Ao usar o campo **Pesquisar** , o número de resultados é exibido para cada categoria de atividade da tela.

![](../assets/palette-filter.png)

## A tela {#canvas}

A **tela** é a zona central do designer de viagem. É nessa zona que você pode soltar suas atividades e configurá-las. Clique em uma atividade na tela para configurá-la. Isso abre o painel de configuração da atividade no lado direito. É possível aumentar e diminuir o zoom usando os botões &quot;+&quot; e &quot;-&quot; no canto superior direito. Na tela de desenho, todas as atividades permitem que você adicione uma próxima etapa após elas, exceto **[!UICONTROL End]** atividades (consulte [](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## O painel de configuração da atividade {#configuration_pane}

O painel **de configuração da** atividade é exibido quando você clica em uma atividade na paleta. Preencha os campos obrigatórios. Clique no **[!UICONTROL Delete]** ícone para excluir a atividade. Clique em **[!UICONTROL Cancel]** para cancelar as modificações ou **[!UICONTROL Ok]** para confirmar. Para excluir atividades, você também pode selecionar uma (ou várias) atividade e pressionar a tecla Backspace. Pressione a tecla escape para fechar o painel de configuração da atividade.

Na tela, suas atividades de ação e evento são representadas por um ícone com o nome do evento ou ação exibido abaixo. No painel de configuração da atividade, é possível usar o **[!UICONTROL Label]** campo para adicionar um sufixo ao nome da atividade. Esses rótulos ajudarão a contextualizar o uso de eventos e ações, especialmente quando você usar o mesmo evento ou ação várias vezes em sua jornada. Você também poderá ver os rótulos adicionados no relatórios do Journey Orchestration.

![](../assets/journey59bis.png)

## As ações da barra superior {#top_actions}

Dependendo do status da jornada, você pode realizar ações diferentes na sua jornada usando os botões disponíveis no canto superior direito: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Esses botões aparecem quando nenhuma atividade é selecionada. Alguns botões serão exibidos contextualmente. O botão de log do modo de teste é exibido quando o modo de teste é ativado (consulte [](../building-journeys/testing-the-journey.md)). O botão relatórios é exibido quando a jornada está ao vivo, parada ou concluída.

![](../assets/journey41.png)

## O uso de caminhos na tela {#paths}

Várias atividades (**[!UICONTROL Condition]**, **[!UICONTROL Action]** atividade) permitem definir uma ação de fallback no caso de um erro ou tempo limite. No painel de configuração da atividade, marque a caixa: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Outro caminho é adicionado após a atividade. A duração do tempo limite é definida nas propriedades da jornada (consulte [](../building-journeys/changing-properties.md) por um usuário administrador). Por exemplo, se um email demorar muito para ser enviado ou estiver com erro, você pode decidir enviar um SMS.

![](../assets/journey42.png)

Várias atividades (evento, ação, espera) permitem que você adicione vários caminhos após eles. Para fazer isso, posicione o cursor na atividade e clique no símbolo &quot;+&quot;. Somente atividades de evento e espera podem ser definidas em paralelo. Se vários eventos forem definidos em paralelo, o caminho escolhido será um dos primeiros eventos que ocorrerem.

Ao ouvir um evento, recomendamos que você não espere o evento indefinidamente. Não é obrigatório, é apenas uma boa prática. Se você quiser ouvir um ou vários eventos apenas durante um determinado tempo, insira um ou vários eventos e uma atividade de espera em paralelo. Consulte [](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Para excluir o caminho, posicione o cursor nele e clique no **[!UICONTROL Delete arrow]** ícone.

![](../assets/journey42ter.png)

Na tela de desenho, quando duas atividades são desconectadas, um aviso é exibido. Coloque o cursor no ícone de aviso para exibir a mensagem de erro. Para corrigir o problema, basta mover a atividade desconectada e conectá-la à atividade anterior.

![](../assets/canvas-disconnected.png)