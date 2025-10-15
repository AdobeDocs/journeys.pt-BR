---
title: Atualização para o Adobe Journey Optimizer
description: Saiba como atualizar para o Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---

# Atualizar o ambiente Journey Orchestration para Adobe Journey Optimizer{#ugrade-ajo}

## O que é o Adobe Journey Optimizer?

O Adobe Journey Optimizer é um aplicativo ágil e escalonável criado originalmente no Adobe Experience Platform para orquestrar e fornecer jornadas personalizadas, conectadas e oportunas ao cliente por meio de qualquer aplicativo, dispositivo, tela ou canal.&#x200B;

## O que é o Journey Orchestration?

O Journey Orchestration é um serviço criado na Adobe Experience Platform que permite adaptar jornadas individuais para cada cliente com base em seu comportamento e preferências anteriores. Journey Orchestration é o aplicativo precursor do Journey Optimizer.

## Por que devo migrar para o Adobe Journey Optimizer?

**Acesso a uma interface simplificada** com recursos de Experience Platform, fornecendo acesso rápido a jornadas, conjuntos de dados, perfis, alertas e muito mais. Não é mais necessário fazer incompatibilidades entre o Adobe Experience Platform e o Journey Orchestration para acessar esquemas ou conjuntos de dados. Tudo está diretamente disponível no Adobe Journey Optimizer. Para obter mais informações, consulte esta [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html?lang=pt-BR).

<table>
<tr>
<th>Antes</th>
<th>Depois</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>Seção Acesso a Jornadas, Segmentos e Administrador (fontes de dados, eventos e ações) no Journey Orchestration. Segmentos e conjuntos de dados podem ser acessados na Adobe Experience Platform. </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>Acesso a Jornadas, Segmentos, Administrador, Segmentos e Conjuntos de Dados, <strong>todos no Adobe Journey Optimizer</strong>. <strong>Os recursos adicionais do Adobe Experience Platform</strong> também estão acessíveis aqui.</p></td>
</tr>
</table>

**Nova interface de relatórios** e acesso a novos recursos de relatórios:

<table>
<tr>
<th>Antes</th>
<th>Depois</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>A exibição global</strong> permite medir o impacto das jornadas e entregas em um período selecionado. Para obter mais métricas em tempo real, você pode acessar a <strong>Visualização dinâmica</strong>. Para cada canal de entrega que está sendo usado em suas jornadas (Email, SMS, Push), uma <strong>seção dedicada</strong> está disponível no relatório para exibir as métricas. Isso se aplica somente se você usar os <strong>recursos de mensagens do Adobe Journey Optimizer</strong> prontos para uso. Entre em contato com a equipe de conta para obter mais informações.</p></td>
</tr>
</table>

Qualquer evolução para melhorar a experiência de relatórios ou enriquecê-la após novas versões de recursos só está disponível na nova interface de relatórios. Comece a usá-lo para obter uma experiência mais completa com o Adobe Journey Optimizer.

Aproveite os benefícios de outros **recursos atuais do Adobe Journey Optimizer** e de novos recursos lançados, como o Controle de Acesso em Nível de Campo e o Controle de Acesso em Nível de Objeto. Entre em contato com a equipe de conta para obter mais informações.

## Como atualizar meu ambiente de Journey Orchestration?

1. Entre em contato com a equipe de conta para atualizar o contrato com a Adobe.

1. Aguarde até que nossa equipe de engenharia conclua a alteração.

1. Atualize suas permissões usando perfis de produto do Journey Optimizer. Consulte esta [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=pt-BR).

1. Agora você tem acesso ao Adobe Journey Optimizer!

## Perguntas frequentes

### Preciso planejar algo para mudar do Journey Orchestration para o Adobe Journey Optimizer?

Não, não há migração, não há necessidade de trabalho, não há tempo de inatividade e nenhum investimento adicional. Você só precisa atualizar seu contrato com o Adobe e nós fazemos o resto. Entre em contato com o representante de conta para obter instruções sobre como iniciar esse processo.

### Perderei algo depois da mudança?

Não, você manterá todos os objetos existentes do Journey Orchestration e do Adobe Experience Platform: esquemas, conjuntos de dados, jornadas, eventos, fontes de dados e ações. Nada será perdido, todas as jornadas ativas continuarão a funcionar sem interrupções.

<table>
<tr>
<th>Antes</th>
<th>Depois</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### Ainda vejo o Journey Orchestration no alternador de aplicativos, é normal?

![](../assets/migration-ajo-9.png)

Sim, é normal. Você ainda poderá ver o item de Journey Orchestration por alguns dias após a atualização. Use o Journey Optimizer.

### O que acontece se eu usar o Journey Orchestration com Adobe Campaign Standard hoje?

Ao mudar para o Adobe Journey Optimizer, você ainda poderá usar a integração entre o Jornada e o Adobe Campaign Standard criando a jornada do cliente no Adobe Journey Optimizer e permitindo que o Adobe Campaign Standard envie o delivery.

No entanto, devido ao funcionamento da pilha de relatórios do Adobe Journey Optimizer, os relatórios não combinarão dados do Jornada e do Campaign Standard. As informações de jornada estarão disponíveis nos relatórios do Adobe Journey Optimizer e as informações de delivery no Adobe Campaign Standard. Uma configuração de Experience Platform pode ser feita para trazer de volta os dados do Adobe Campaign Standard para o Adobe Experience Platform, disponibilizando-os para o Customer Journey Analytics ([saiba mais](https://business.adobe.com/br/products/experience-platform/customer-journey-analytics.html)) ou outras ferramentas de relatório de terceiros, como Tableau ou PowerBI.

Os relatórios do Adobe Journey Optimizer funcionam melhor ao usar os recursos de mensagens prontos para uso da Adobe Journey Optimizer (disponíveis em ofertas dedicadas da Adobe Journey Optimizer). Para obter mais informações sobre como as mensagens podem ser criadas na tela de jornada, consulte esta [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html?lang=pt-BR).

Entre em contato com a equipe de conta para obter mais informações.
