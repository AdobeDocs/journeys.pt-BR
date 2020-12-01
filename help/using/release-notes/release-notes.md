---
product: adobe campaign
solution: Journey Orchestration
title: Notas de versão
description: Saiba mais sobre as notas de versão
translation-type: tm+mt
source-git-commit: fe34587181d284944ce1af64b12ad1185c59f890
workflow-type: tm+mt
source-wordcount: '2055'
ht-degree: 77%

---


# Notas de versão {#release-notes}

Esta página lista todos os novos recursos e melhorias do Journey Orchestration.
Você também pode consultar as [Atualizações de documentação](../release-notes/documentation-updates.md).

## Versão de novembro de 2020 {#november-release}

<table>
<thead>
<tr>
<th><strong>Saltando de uma viagem para outra</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adicionamos uma nova atividade de ação que permite que você empurre indivíduos de uma jornada para outra. A atividade Jump permite:
</p>
<ul>
<li>simplificar a concepção de viagens muito complexas, dividindo-as em várias </li>
<li>construir viagens baseadas em padrões de viagem comuns e reutilizáveis</li>
</ul>
<p>Para obter mais informações, consulte a <a href="../building-journeys/jump.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Uso de propriedades de jornada no editor de expressões</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>No editor de expressões avançada, adicionamos uma nova categoria à lista de campos e funções. Esta é a informação obtida pelo sistema a partir de viagens em vida, como a identificação da viagem ou os erros específicos encontrados. Isso lhe dará mais possibilidades ao construir suas viagens. Por exemplo, você poderá alertar sistemas de terceiros em caso de erros encontrados em uma condição ou ação.
</p>
<p>Observe que esse recurso estará disponível nos próximos dias.</p>
<p>Para obter mais informações, consulte a <a href="../expression/journey-properties.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos com base em regras (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adicionamos um novo método para configurar seus eventos mais facilmente. Esse recurso, que foi testado entre um conjunto limitado de clientes por meio do programa Alpha, está agora disponível em Beta para todos os clientes. Esse novo método não exige o uso de eventID. Ele avalia se o evento deve ser acionado de acordo com uma condição. Você ainda pode usar o método existente, agora chamado de "gerado pelo sistema".
</p>
<p>Observe que esse recurso estará disponível nos próximos dias.</p>
<p>Para obter mais informações, consulte a <a href="../event/about-events.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Outras melhorias{#october-november}

Foram adicionadas limitações ao criar novas versões de uma jornada. Essas limitações evitam mudanças drásticas demais na jornada para manter alguma consistência entre as versões. [Leia mais](../about/limitations.md#journey-versions-limitations)

A atividade **Qualificação de segmento** não pode mais ser usada em uma jornada que inclui atividades de mensagem de Campaign Standard. Essa restrição protege a integridade das instâncias do Adobe Campaign Standard. Na verdade, o uso da Qualificação de segmento pode levar a picos diários de envio de mensagens que sobrecarregariam o envio de mensagens transacionais Campaign Standard. [Leia mais](../about/limitations.md#segment-qualification)

## Versão de outubro de 2020 {#october-release}

<table>
<thead>
<tr>
<th><strong>Tempo limite do evento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Agora você pode configurar um tempo limite para um evento para fazer uma jornada ouvir um evento somente durante um determinado tempo. Não é mais necessário adicionar uma atividade de espera em paralelo ao caminho do evento para conseguir isso.
</p>
<p>Para obter mais informações, consulte a <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Outras melhorias{#october-other}

* Quando você publica uma nova versão de uma jornada, a versão anterior automaticamente termina e alterna para o status Fechado. [Leia mais](../building-journeys/journey-versions.md)

## Versão de setembro de 2020 {#september-release}

### Atualizações do GA{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Melhorias na atividade da condição</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Ao adicionar condições à sua jornada, agora você pode definir um rótulo. Se você usar várias condições em uma jornada, isso permite que você as identifique mais facilmente.
</p>
<p>Para obter mais informações, consulte a <a href="../building-journeys/condition-activity.md#about_condition">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

### Atualizações Alfa{#september-alpha-update}

Para saber mais sobre o escopo do Alfa, consulte esta [seção](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Ler melhorias na atividade do segmento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>As seguintes melhorias foram feitas na atividade <strong>Read segment</strong>:
</p>
<ul>
<li><p>As viagens baseadas em segmentos agora exibem, acima da tela, um lembrete do tipo de programação da jornada. Você pode clicar neste lembrete para acessar o menu de configuração do agendamento.</p>
</li>
<li><p>A granularidade dos logs de modo de teste foi aprimorada para exibir o status de progresso de exportação do segmento.</p>
</li>
</ul>
<p>Para obter mais informações sobre a atividade <strong>Read segment</strong>, consulte a <a href="../alpha/alpha-segment-trigger.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

## Versão de agosto de 2020 {#august-release}

### Atualizações do GA{#august-ga-update}

Agora o payload dos eventos de qualificação de segmento contém as seguintes informações de contexto, que podem ser usadas em condições e ações: o comportamento (entrada, saída), a data e hora da qualificação e a ID do segmento. [Leia mais](../building-journeys/segment-qualification-events.md)

### Atualizações Alfa{#august-alpha-update}

Para saber mais sobre o escopo do Alfa, consulte esta [seção](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Atividade do acionador de segmento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>As seguintes melhorias foram implantadas na atividade do acionador de segmento:
</p>
<ul>
<li><p>O nome da atividade foi alterado para "Ler segmento". </p>
</li>
<li><p>A configuração do scheduler de jornada foi removida das propriedades da atividade. Agora ela pode ser acessada diretamente nas Propriedades da jornada, em uma seção dedicada que será exibida se uma atividade Ler segmento tiver sido colocada na tela. </p>
</li>
<li><p>Agora você pode testar a jornada em um perfil unitário e acompanhar seu progresso na jornada usando o fluxo visual.</p>
</li>
</ul>
<p>Para obter mais informações, consulte a <a href="../alpha/alpha-segment-trigger.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos com base em regras</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>As seguintes melhorias foram realizadas em eventos baseados em regras:
</p>
<ul>
<li><p>Agora você pode aproveitar todos os dados de evento comportamental do Adobe Analytics que já estão sendo capturados e transmitidos na plataforma para acionar jornadas e automatizar experiências para seus clientes. <a href="../event/about-analytics.md">Leia mais</a></p>
</li>
<li><p>A partir de agora, ao acionar um evento com base em regras no modo de teste, será possível visualizar diretamente a condição da ID do evento. Além disso, uma dica de ferramenta foi adicionada ao lado de cada campo de avaliação da regra. <a href="../building-journeys/testing-the-journey.md#test-rule-based">Leia mais</a></p>
</li>
<li><p>A tela de definição de evento com base em regras foi reorganizada para obter uma experiência avançada. <a href="../event/about-creating.md">Leia mais</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Versão Alfa - Julho de 2020 {#alpha-release---july-2020}

O programa Alfa oferece recursos que estão sendo atualmente testados em um conjunto limitado de clientes. Ele permite a melhoria do produto com base no feedback recebido. Esses recursos não estão disponíveis para todos os clientes do Journey Orchestration.

Esses recursos são descritos em uma [seção](../alpha/alpha-overview.md) específica.

<table>
<thead>
<tr>
<th><strong>Interface do usuário aprimorada</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A navegação nos menus do Journey Orchestration foi aprimorada para fornecer uma interface consistente com a Adobe Experience Platform:
</p>
<ul>
<li><p>Os menus foram movidos de cima para o lado esquerdo da interface. </p>
</li>
<li><p>Agrupamento de funcionalidades do administrador em um único painel.</p>
</li>
</ul>
<p>Para obter mais informações, consulte a <a href="../alpha/alpha-interface.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Atividade do acionador de segmento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A atividade do acionador de segmento permite que todos os indivíduos pertencentes a um segmento da Adobe Experience Platform possam entrar em uma jornada. A entrada em uma jornada pode ser efetuada uma vez ou regularmente. <a href="../alpha/alpha-segment-trigger.md">Leia mais</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventos com base em regras</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Simplificamos a forma como você configura os eventos na experiência. Estamos introduzindo um novo método que não requer o uso de uma ID de evento. Agora é possível definir um evento com base em regras ao configurar seu evento no Journey Orchestration. <a href="../event/about-events.md">Leia mais</a>
</p>
</td>
</tr>
</tbody>
</table>


## Versão do segundo trimestre - Junho de 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Aprimoramentos de integração da Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Foram realizados os seguintes aprimoramentos de integração na Adobe Experience Platform:</p>
<ul>
<li><p>Uma nova atividade permite que a escuta das entradas/saídas do segmento da Adobe Experience Platform possibilite a entrada ou o avanço das pessoas em uma jornada. <a href="../building-journeys/segment-qualification-events.md">Leia mais</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Graças à nova guia <strong>Segmentos</strong>, agora os segmentos da Adobe Experience Platform podem ser criados e editados sem precisar sair da interface do Journey Orchestration. <a href="../segment/about-segments.md">Leia mais</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>No editor de expressões simples, os segmentos da Adobe Experience Platform são agora listados diretamente na árvore de navegação para permitir uma fácil configuração de condições como "essa pessoa pertence ao segmento A?". <a href="../segment/using-a-segment.md">Leia mais</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Agora o Journey Orchestration transmite automaticamente as etapas executadas nas jornadas para a Adobe Experience Platform. inclusive possíveis erros que podem ser encontrados. Essas informações podem ser usadas para obter relatórios e solução de problemas executando consultas nos eventos Journey Step para uma determinada jornada ou para todas as jornadas. <a href="../building-journeys/sharing-overview.md">Leia mais</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Agora o Journey Orchestration pode ser conectado às sandboxes de produção e não produção da Adobe Experience Platform. Observe que as sandboxes são um recurso beta. <a href="../about/access-management.md#sandboxes">Leia mais</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aprimoramentos no designer da jornada e no modo de teste</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Foram feitos os seguintes aprimoramentos ao designer da jornada e ao modo de teste:</p>
<ul>
<li><p>Agora você pode copiar e colar atividades de uma jornada para outra, selecionando 1 ou N atividades da jornada. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Leia mais</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Após o disparo de um evento para fazer um perfil de teste entrar em uma jornada, você pode ver o progresso ao longo da jornada graças a um fluxo visual colorido. Em caso de erro na jornada, detalhes do erro também serão exibidos. <a href="../building-journeys/testing-the-journey.md#firing_events">Leia mais</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>O estado da jornada <strong>Concluído</strong> foi renomeado para <strong>Fechado (sem entrada)</strong> para refletir melhor o significado do estado.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Outras melhorias**

Para evitar o envio de muitas chamadas de API para sistemas de terceiros, estamos introduzindo uma nova API pública para configurar regras de &quot;limitação&quot;. As regras de limitação permitem a definição de um número máximo de chamadas para um ponto de entrada de API por milissegundos. [Leia mais](../api/capping.md)

O controle de acesso agora permite mais granularidade no gerenciamento de acesso do usuário. Disponível a partir de 30 de junho de 2020. [Leia mais](../about/access-management.md#create-product-profile)

Agora o Journey Orchestration também está disponível no APAC (Centro de dados australiano). Disponível a partir de 30 de junho de 2020

A interface do Journey Orchestration está disponível em japonês.

## Versão do primeiro trimestre - Março de 2020 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>Melhorias no modo de teste</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>As seguintes melhorias foram feitas no modo de teste:</p>
<ul>
<li>Quando uma jornada usa vários eventos, é possível acionar cada um deles individualmente a partir de uma lista suspensa na tela <strong>Configuração de evento</strong> do modo de teste. <a href="../building-journeys/testing-the-journey.md#firing_events">Leia mais</a></p></li>
<li><p>Quando uma ou mais atividades de <strong>espera</strong> são usadas em uma jornada, é possível definir o tempo que cada uma dessas atividades durará no modo de teste. O tempo padrão é de 10 segundos. Você pode alterar a duração usando o parâmetro<strong>Tempo de espera no teste</strong>, no canto inferior esquerdo. <a href="../building-journeys/testing-the-journey.md">Leia mais</a></p><img src="../assets/rn-test.png"/>
</li>
<li>Nos <strong>logs de teste</strong>, em caso de erro ao chamar um sistema de terceiros (fonte de dados ou ação), o código de erro e a resposta do erro agora são exibidos. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Leia mais</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gerenciamento centralizado de fuso horário</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>O gerenciamento de fuso horário agora está centralizado no painel de propriedades da jornada. Foram adicionados dois parâmetros às propriedades de jornada:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>A lista suspensa <strong>Fuso horário</strong> permite selecionar um fuso horário específico. Por padrão, é usado o fuso horário do navegador. </li>
<li>A caixa de seleção <strong>Fuso horário do perfil</strong> permite usar o fuso horário do perfil da Adobe Experience Platform da pessoa que entra na jornada, caso esteja disponível. Caso contrário, é utilizado o fuso horário definido na lista suspensa. Este recurso não é compatível com jornadas que utilizam eventos sem namespace.</li>
</ul>
<p>Para obter mais informações, consulte as seções <a href="../building-journeys/changing-properties.md#timezone">Alteração de propriedades</a> e <a href="../building-journeys/timezone-management.md">Gerenciamento de fuso horário</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Melhorias no designer de jornadas</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>A <strong>paleta</strong> da jornada, no lado esquerdo do designer de jornada, foi aprimorada:</p>
<ul>
<li>Um novo ícone, ao lado da barra de <strong>Pesquisa</strong>, permite ocultar ou exibir elementos indisponíveis na paleta, por exemplo, os eventos que usam um namespace diferente daqueles usados em sua jornada. Por padrão, os itens indisponíveis ficam ocultos.</li>
<li>Ao usar o campo <strong>Pesquisa</strong>, o número de resultados para cada categoria de atividade da tela agora é exibido.</li>
<li>A navegação entre as diferentes categorias de atividade foi aprimorada.</li>
</ul>
<p>No designer de jornada, você pode verificar se está acessando a versão mais recente da jornada. Essas informações são exibidas ao lado do número da versão.</p>
<p>Na <strong>tela</strong> da jornada, quando duas atividades são desconectadas, uma mensagem de aviso é exibida.</p>
<img src="../assets/rn-canvas.png"/>
<p>Para obter mais informações, consulte a <a href="../building-journeys/using-the-journey-designer.md">documentação detalhada</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Ajuda contextual</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Uma ajuda contextual agora está disponível nas diferentes telas de lista do Journey Orchestration (jornadas, eventos, ações e fontes de dados). A ajuda permite visualizar uma descrição rápida da funcionalidade atual e acessar artigos e vídeos relacionados.</p>
<p>Para exibir a ajuda contextual, clique no ícone <img src="../assets/icon-context.png"/> no canto superior direito da tela. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Outras melhorias**

* Além dos EUA, o Journey Orchestration agora está disponível na **Europa, no Oriente Médio e na África**. O aplicativo e a documentação estão disponíveis em francês e alemão.

* A Experience League agora está integrada ao produto, o que simplifica o acesso ao conteúdo relacionado e ajuda a aproveitar ao máximo a Experience Cloud. O acesso direto à documentação do Journey Orchestration está disponível na parte inferior da guia Ajuda. Além disso, clique em Ajuda > Feedback para reportar problemas ou compartilhar suas ideias com a Adobe.

* O atalho **C** do teclado, que permite criar um novo item, agora está disponível em todas as telas de lista: jornadas, fontes de dados, ações e eventos. [Leia mais](../about/user-interface.md#section_ksq_zr1_ffb)

* Agora você pode **excluir** as jornadas interrompidas. Os relatórios associados a essas jornadas excluídas não estarão disponíveis.

* Ao navegar pelos **campos da Adobe Experience Platform** (formato XDM), você verá o nome de exibição além do nome do campo. Essas informações são recuperadas a partir da definição do schema no Modelo de dados de experiência. Quando disponível, o nome de exibição alternativo é exibido. Essa descrição simples, especialmente útil no caso de campos eVar, permite identificar os campos mais facilmente. [Leia mais](../about/user-interface.md#friendly-names-display)

## Última Versão - Dezembro de 2019 {#ga-release---december-2019}

O Journey Orchestration agora está pronta.

Crie casos de uso de orquestração em tempo real usando dados contextuais armazenados em eventos ou fontes de dados.

O Journey Orchestration permite a orquestração em tempo real com dados contextuais de eventos, informações da Adobe Experience Platform ou dados de serviços de API de terceiros. O aplicativo determina, em fluxos multi-fases chamados jornadas, as melhores próximas ações específicas para o consumidor, de acordo com o perfil e o comportamento. Inclui o momento ideal e o tipo de ação, como enviar ao consumidor uma notificação por push por meio dos recursos de mensagens transacionais do Adobe Campaign Standard (é preciso ter o Adobe Campaign Standard) ou a notificação de um sistema de terceiros. Essas decisões são tomadas com base em regras e pontuações do Sensei.

[](../action/working-with-adobe-campaign.md)Saiba mais sobre o Journey Orchestration.

Recursos adicionais:

* [Tutoriais](https://docs.adobe.com/content/help/pt-BR/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Comunidade](https://www.adobe.com/go/journeyorchestrationcommunity)
