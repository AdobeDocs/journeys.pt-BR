---
product: adobe campaign
title: A interface do usuário
description: Saiba mais sobre a interface do usuário
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 93%

---

# Interface do usuário{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Para tirar o melhor proveito do [!DNL Journey Orchestration], recomendamos a utilização do Chrome como navegador de Internet. A interface é exibida no idioma definido no IMS. Se o seu idioma IMS não for aceito pelo [!DNL Journey Orchestration], a interface será exibida em inglês.
>
>Esta documentação é atualizada com frequência para refletir as alterações recentes no produto. Entretanto, algumas capturas de tela podem diferir ligeiramente da interface do produto.

## Acessar o [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Para acessar o [!DNL Journey Orchestration]na interface do , clique no botão **[!UICONTROL App Selector]** ícone , na parte superior direita e clique em **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

Você também pode acessar o [!DNL Journey Orchestration] na página inicial da Experience Cloud, na seção **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## Descobrir a interface{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Sobre a lista da jornada"
>abstract="A lista de jornadas permite visualizar todas as suas jornadas de uma só vez, ver seu status e executar ações básicas."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Assista ao vídeo de demonstração"

Os menus superiores permitem navegar por diferentes funcionalidades do [!DNL Journey Orchestration]: **[!UICONTROL Home]**(as jornadas),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Clique no ícone ![](../assets/icon-context.png) no canto superior direito da tela para exibir a ajuda contextual. Ela está disponível em diferentes telas de lista [!DNL Journey Orchestration] (jornadas, eventos, ações e fontes de dados). A ajuda permite visualizar uma descrição rápida da funcionalidade atual e acessar artigos e vídeos relacionados.

![](../assets/journey2bis.png)

## Pesquisa e filtragem{#section_lgm_hpz_pgb}

Em **[!UICONTROL Home]**,**[!UICONTROL Data Sources]**, **[!UICONTROL Events]** e **[!UICONTROL Actions]** listas, uma barra de pesquisa permite procurar um item.

Os **[!UICONTROL Filters]** podem ser acessados com um clique no ícone de filtro na parte superior esquerda da lista. O menu de filtros permite filtrar os elementos exibidos de acordo com diferentes critérios. Você pode optar por exibir apenas os elementos de um determinado tipo ou status, os que você criou ou os que foram modificados nos últimos 30 dias.

Nas listas **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** e **[!UICONTROL Actions]**, use **[!UICONTROL Creation filters]** para filtrar a data de criação e o usuário. Por exemplo, você pode optar por exibir somente os eventos criados nos últimos 30 dias.

Na lista jornada (em **[!UICONTROL Home]**), além do **[!UICONTROL Creation filters]**, você também pode filtrar as jornadas exibidas de acordo com seu status, tipo e versão (**[!UICONTROL Status and version filters]**). O tipo pode ser: **[!UICONTROL Unitary event]** ou **[!UICONTROL Segment qualification]**. Você também pode optar por exibir somente as jornadas que usam um evento, grupo de campos ou ação específica (**[!UICONTROL Activity filters]** e **[!UICONTROL Data filters]**). O **[!UICONTROL Publication filters]** permite selecionar uma data de publicação ou usuário. Você pode optar, por exemplo, por exibir somente as versões mais recentes de jornadas ao vivo que foram publicadas ontem. Consulte [esta página](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Observe que as colunas exibidas podem ser personalizadas usando o botão de configuração na parte superior direita das listas. A personalização é salva para cada usuário.

As colunas **[!UICONTROL Last update]** e **[!UICONTROL Last update by]** exibem quando ocorreu a última atualização de suas jornadas e qual usuário a operou.

![](../assets/journey74.png)

Nos painéis de configuração de evento, fonte de dados e ação, o campo **[!UICONTROL Used in]** exibe o número de jornadas que usam esse evento, grupo de campos ou ação em particular. Você pode clicar no botão **[!UICONTROL View journeys]** para exibir a lista de jornadas correspondentes.

![](../assets/journey3bis.png)

Nas diferentes listas, é possível executar ações básicas em cada elemento. Por exemplo, você pode duplicar ou excluir um item.

![](../assets/journey4.png)

## Navegação pelos campos da Adobe Experience Platform {#friendly-names-display}

Ao definir a [carga útil do evento](../event/defining-the-payload-fields.md), [carga útil do grupo de campo](../datasource/field-groups.md) e selecionar campos no [editor de expressões](../expression/expressionadvanced.md), o nome de exibição é exibido além do nome do campo. Essas informações são recuperadas a partir da definição do schema no modelo de dados de experiência.

Se descritores como &quot;xdm:alternateDisplayInfo&quot; forem fornecidos durante a configuração de schemas, os nomes de usuário simples substituirão os nomes de exibição. É especialmente útil ao trabalhar com &quot;eVars&quot; e campos genéricos. Você pode configurar descritores de nome simples por meio de uma chamada de API. Para obter mais informações, consulte o [guia do desenvolvedor do Registro de Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=pt-BR).

![](../assets/xdm-from-descriptors.png)

Se um nome simples estiver disponível, o campo será exibido como `<friendly-name>(<name>)`. Se nenhum nome simples estiver disponível, o nome de exibição será exibido, por exemplo `<display-name>(<name>)`. Se nenhum deles estiver definido, somente o nome técnico do campo será exibido `<name>`.

>[!NOTE]
>
>Os nomes simples não são recuperados ao selecionar campos de uma união de schemas.

## Acessibilidade{#accessibility}

Os recursos de acessibilidade do Adobe Journey Optimizer são fornecidos pela Adobe Experience Platform:

* Acessibilidade do teclado
* Contraste de cores
* Validação de campos obrigatórios

[Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=pt-BR){target="_blank"} na documentação da Adobe Experience Platform.

Você pode usar esses atalhos de teclado comuns no Adobe Journey Optimizer:

| Ação | Atalho |
| --- | --- |
| Mover entre elementos da interface do usuário, seções e grupos de menu | Guia |
| Retroceder entre elementos da interface do usuário, seções e grupos de menu | Shift + Tab |
| Mover dentro de seções para definir o foco de elementos individuais | Seta |
| Selecionar ou limpar um elemento em foco | Enter ou Barra de espaço |
| Cancelar uma seleção, recolher um painel ou fechar uma caixa de diálogo | Esc |

[Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html?lang=pt-BR){target="_blank"} na documentação da Adobe Experience Platform.

Você pode usar esses atalhos em partes específicas do Journey Optimizer:

<table>
  <thead>
    <tr>
      <th>Elemento da interface</th>
      <th>Ação</th>
      <th>Atalho</th>
    </tr>
  </thead>
  <tr>
    <td>Lista de jornadas, ações, fontes de dados ou eventos</td>
    <td>Criar uma jornada, uma ação, uma fonte de dados ou um evento</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Tela da jornada no status de rascunho</td>
    <td>Adicionar uma atividade da paleta esquerda na primeira posição disponível, de cima para baixo</td>
    <td>Clique duas vezes na atividade</td>
  </tr>
  <tr>
    <td>Selecione todas as atividades</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td>Excluir as atividades selecionadas</td>
    <td>Delete ou Backspace, em seguida, tecle Enter para confirmar a exclusão</td>
  </tr>
  <tr>
  <td rowspan="3">

Painel de configuração destes elementos:

<ul>
  <li>Atividade em uma jornada</li>
  <li>Evento</li>
  <li>Fonte de dados</li>
  <li>Ação</li>
</ul>

</td>
    <td>Mover para o próximo campo a ser configurado</td>
    <td>Guia</td>
  </tr>
  <tr>
    <td>Salve as alterações e feche o painel de configuração</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>Descartar alterações e fechar o painel de configuração</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">Jornada no modo de teste</td>
    <td>Ative ou desative o modo de teste</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Acionar um evento em uma jornada baseada em eventos</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Acione um evento em uma jornada baseada em segmento para a qual a opção **[!UICONTROL Single profile at a time]** esteja ativada

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Exibir os logs de teste</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Campo de texto</td>
    <td>Selecionar todo o texto no campo selecionado</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Janela pop-up</td>
    <td>Salvar alterações ou confirmar a ação</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>Fechar a janela</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Editor de expressão simples</td>
    <td>Selecionar e adicionar um campo</td>
    <td>Clique duas vezes em um campo</td>
  </tr>
  <tr>
    <td>Navegar pelos campos XDM</td>
    <td>Selecionar todos os campos de um nó</td>
    <td>Selecione o nó principal</td>
  </tr>
  <tr>
    <td>Visualização do conteúdo</td>
    <td>Selecionar o conteúdo</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
</table>
