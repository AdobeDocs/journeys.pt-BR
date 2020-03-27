---
title: A interface do usuário
description: Saiba mais sobre a interface do usuário
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bc5b29eefa4d787cd448352252823a616489d8c8

---


# Interface do usuário{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Para tirar o melhor proveito do Journey Orchestration, recomendamos usar o Chrome como navegador da Internet.
>
>Esta documentação é atualizada com frequência para refletir as alterações recentes no produto. Entretanto, algumas capturas de tela podem diferir ligeiramente da interface do produto.

## Acessar a orquestração de jornada{#accessing_journey_orchestration}

Para acessar a interface do Journey Orchestration, clique no **[!UICONTROL App Selector]** ícone, na parte superior direita. Em seguida, clique **[!UICONTROL Journey Orchestration]**, no lado direito, abaixo de &quot;Plataforma de experiência&quot;.

![](../assets/journey1.png)

Você também pode acessar o Journey Orchestration a partir do home page da Experience Cloud, na **[!UICONTROL Quick access]** seção.

![](../assets/journey1bis.png)

## Descobrir a interface{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;Sobre a lista da jornada&quot;
>abstract=&quot;A lista de viagem permite que você visualização todas as suas viagens de uma só vez, veja seu status e execute ações básicas. Você pode duplicado, parar ou excluir suas viagens. Dependendo da jornada, certas ações podem não estar disponíveis. Por exemplo, você não pode excluir ou reiniciar uma jornada que esteja concluída. Você pode criar uma nova versão ou duplicado-a. Você também pode usar a barra de pesquisa para procurar uma jornada.&quot;
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Assista ao vídeo de demonstração&quot;

Os menus superiores permitem navegar pelas diferentes funcionalidades da Journey Orchestration: **[!UICONTROL Home]**(as viagens),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Clique no ![](../assets/icon-context.png) ícone no canto superior direito da tela para exibir a ajuda contextual. Ele está disponível em diferentes telas de lista da Journey Orchestration (viagens, eventos, ações e fontes de dados). Isso permite que você visualização uma descrição rápida da funcionalidade atual e acesse artigos e vídeos relacionados.

![](../assets/journey2bis.png)

## Pesquisa e filtragem{#section_lgm_hpz_pgb}

Nas **[!UICONTROL Home]** listas,**[!UICONTROL Data Sources]****[!UICONTROL Events]** e **[!UICONTROL Actions]** , uma barra de pesquisa permite que você procure um item.

Para **[!UICONTROL Filters]** acessá-lo, clique no ícone de filtro na parte superior esquerda da lista. O menu filtros permite que você filtre os elementos exibidos de acordo com critérios diferentes. Você pode optar por exibir apenas os elementos de um determinado tipo ou status, os que você criou ou os que foram modificados nos últimos 30 dias.

Nas **[!UICONTROL Data Sources]** listas, **[!UICONTROL Events]** e **[!UICONTROL Actions]** , use os filtros **de** criação para filtrar a data de criação e o usuário. Por exemplo, você pode optar por exibir somente os eventos criados nos últimos 30 dias.

Na lista de viagem (abaixo **[!UICONTROL Home]**), além do **[!UICONTROL Creation filters]**, você também pode filtrar as viagens exibidas de acordo com seu status e versão (**[!UICONTROL Status and version filters]**). Você também pode optar por exibir somente as jornadas que usam um evento, grupo de campos ou ação específicos (**[!UICONTROL Activity filters]** e **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** Permite selecionar uma data de publicação ou usuário. Você pode optar, por exemplo, por exibir apenas as versões mais recentes de viagens ao vivo que foram publicadas ontem. Consulte [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Observe que as colunas exibidas podem ser personalizadas usando o botão de configuração na parte superior direita das listas. A personalização é salva para cada usuário.

As colunas **[!UICONTROL Last update]** e **[!UICONTROL Last update by]** permitem exibir quando ocorreu a última atualização de suas viagens e qual usuário a operou.

![](../assets/journey74.png)

Nos painéis de configuração de evento, fonte de dados e ação, o **[!UICONTROL Used in]** campo exibe o número de viagens que usam esse evento, grupo de campos ou ação em particular. Você pode clicar no **[!UICONTROL View journeys]** botão para exibir a lista de viagens correspondentes.

![](../assets/journey3bis.png)

Nas diferentes listas, é possível executar ações básicas em cada elemento. Por exemplo, você pode duplicado ou excluir um item.

![](../assets/journey4.png)

## Navegação pelos campos da Plataforma de dados {#friendly-names-display}

Ao definir a carga [do](../event/defining-the-payload-fields.md)evento, a carga [do grupo de](../datasource/field-groups.md) campos e a seleção de campos no editor [de](../expression/expressionadvanced.md)expressões, o nome de exibição é exibido além do nome do campo. Essas informações são recuperadas da definição do schema no Modelo de dados de experiência.

Se descritores como &quot;xdm:alternativoDisplayInfo&quot; forem fornecidos durante a configuração de schemas, os nomes amigáveis substituirão os nomes de exibição. É especialmente útil ao trabalhar com &quot;eVars&quot; e campos genéricos.Você pode configurar descritores de nome amigáveis por meio de uma chamada de API. Para obter mais informações, consulte o guia [do desenvolvedor do Registro do](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)Schema.

![](../assets/xdm-from-descriptors.png)

Se um nome amigável estiver disponível, o campo será exibido como `<friendly-name>(<name>)`. Se nenhum nome amigável estiver disponível, o nome de exibição será exibido, por exemplo `<display-name>(<name>)`. If none of them are defined, only the technical name of the field will be displayed `<name>`.

>[!NOTE]
>
>Friendly names are not retrieved when you select fields from a union of schemas.

## Using the different shortcuts{#section_ksq_zr1_ffb}

Here are the different shortcuts available in the Journey Orchestration&#39;s interface.

_In the list of journeys, actions, data sources or events:_

* Press **c** to create a new journey, action, data source or event.

_Ao configurar uma atividade em uma jornada:_

The canvas is automatically saved. You can see, on the top left of the canvas, the saving status.

* Press **escape** to close the configuration pane and discard the changes made. This is the equivalent of the **[!UICONTROL Cancel]** button.
* Press **[!UICONTROL Enter]** or click outside the pane to close the configuration pane. Changes are saved. Isso é o equivalente ao **[!UICONTROL Ok]** botão.
* Se pressionar **[!UICONTROL Delete]** ou **usar o backspace**, pressione **[!UICONTROL Enter]** para confirmar a exclusão.

_Em pop-ups:_

* Pressione **escape** para fechá-lo (equivalente ao botão **Cancel (Cancelar** ).
* Press **[!UICONTROL Enter]** to save or confirm (equivalent of the **[!UICONTROL Ok]** or **[!UICONTROL Save]** button).

_No painel de configuração do evento, da fonte de dados ou da ação:_

* Pressione **escape** para fechar o painel de configuração sem salvar.
* Press **[!UICONTROL Enter]** to save modifications and close the configuration pane.
* Press **tab** to jump between the different fields to configure.

_No editor de expressões simples_

* Clique com o Duplo em um campo, à esquerda, para adicionar um query (equivalente a arrastar e soltar).

_Ao navegar pelos campos XDM:_

* Marcar um &quot;nó&quot; selecionará todos os campos do nó.

_Em todas as áreas de texto:_

* Use a combinação de teclas **Ctrl/Command + A** para selecionar o texto. Na pré-visualização de carga, seleciona a carga.

_Em uma tela com uma barra de pesquisa:_

* Use a combinação de teclas **Ctrl/Command + F** para selecionar a barra de pesquisa.

_Na tela de uma jornada:_

* Use a combinação de teclas **Ctrl/Command + A** para selecionar todas as atividades.
* Quando uma ou várias atividades forem selecionadas, pressione **[!UICONTROL Delete]** ou **backspace** para excluí-las. Em seguida, pressione **[!UICONTROL Enter]** para confirmar no pop-up de confirmação.
* Clique com o Duplo do mouse em uma atividade da paleta esquerda para adicioná-la à primeira posição disponível (de cima para baixo).
