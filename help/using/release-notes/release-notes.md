---
title: Notas de versão
description: Saiba mais sobre as notas de versão
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d
workflow-type: ht
source-wordcount: '758'
ht-degree: 100%

---


# Notas de versão {#release-notes}

Esta página lista todos os novos recursos e melhorias do Journey Orchestration.
Você também pode consultar as [Atualizações de documentação](../release-notes/documentation-updates.md).

## Versão do primeiro trimestre - Março de 2020 {#q1-release---march-2020}

**Novidades**

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
<li>A caixa de seleção <strong>Fuso horário do perfil</strong> permite usar o fuso horário do perfil da Experience Platform da pessoa que entra na jornada, caso esteja disponível. Caso contrário, é utilizado o fuso horário definido na lista suspensa. Este recurso não é compatível com jornadas que utilizam eventos sem namespace.</li>
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

* Ao navegar pelos **campos da Plataforma de dados** (formato XDM), você verá o nome de exibição além do nome do campo. Essas informações são recuperadas a partir da definição do schema no Modelo de dados de experiência. Quando disponível, o nome de exibição alternativo é exibido. Essa descrição simples, especialmente útil no caso de campos eVar, permite identificar os campos mais facilmente. [Leia mais](../about/user-interface.md#friendly-names-display)

## Última Versão - Dezembro de 2019 {#ga-release---december-2019}

O Journey Orchestration agora está pronta.

Crie casos de uso de orquestração em tempo real usando dados contextuais armazenados em eventos ou fontes de dados.

O Journey Orchestration permite a orquestração em tempo real com dados contextuais de eventos, informações da Adobe Experience Platform ou dados de serviços de API de terceiros. O aplicativo determina, em fluxos multi-fases chamados jornadas, as melhores próximas ações específicas para o consumidor, de acordo com o perfil e o comportamento. Inclui o momento ideal e o tipo de ação, como enviar ao consumidor uma notificação por push por meio dos recursos de mensagens transacionais do Adobe Campaign Standard (é preciso ter o Adobe Campaign Standard) ou a notificação de um sistema de terceiros. Essas decisões são tomadas com base em regras e pontuações do Sensei.

[](../action/working-with-adobe-campaign.md)Saiba mais sobre o Journey Orchestration.

Recursos adicionais:

* [Tutoriais](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Comunidade](https://www.adobe.com/go/journeyorchestrationcommunity)
