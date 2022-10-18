---
title: Migrar para o Adobe Journey Optimizer
description: Saiba como migrar para o Adobe Journey Optimizer
hide: true
hidefromtoc: true
source-git-commit: 19760b779c2b105286d502b3bf4edda5bec79194
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 3%

---


# Atualize seu ambiente do Journey Orchestration para o Adobe Journey Optimizer{#migration-jo}

## O que é o Adobe Journey Optimizer?

O Adobe Journey Optimizer é um aplicativo ágil e escalável criado originalmente na Adobe Experience Platform para orquestrar e fornecer jornadas personalizadas, conectadas e oportunas para clientes em qualquer aplicativo, dispositivo, tela ou canal. &#x200B;

## O que é o Adobe Journey Orchestration?

O Journey Orchestration é um serviço criado na Adobe Experience Platform que permite personalizar jornadas individuais para cada cliente com base em seu comportamento e preferências anteriores. O Journey Orchestration é o aplicativo precursor para a Journey Optimizer.

## Por que devo migrar para o Adobe Journey Optimizer?

**Acesso a uma interface simplificada** com recursos do Experience Platform que fornecem acesso rápido a jornadas, conjuntos de dados, perfis, alertas e muito mais. Não é mais necessário fazer isso entre o Adobe Experience Platform e o Journey Orchestration para acessar esquemas ou conjuntos de dados, tudo está diretamente disponível no Adobe Journey Optimizer. Para obter mais informações, consulte esta [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>Antes</th>
<th>Depois</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>Acesso a Jornada, segmentos e seção de administração (fontes de dados, eventos e ações) no Journey Orchestration. Segmentos e conjuntos de dados podem ser acessados no Adobe Experience Platform. </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>Acesso a Jornadas, segmentos, administração, segmentos e conjuntos de dados, <strong>tudo no Adobe Journey Optimizer</strong>. <strong>Recursos adicionais do Adobe Experience Platform</strong> também podem ser acessadas aqui.</p></td>
</tr>
</table>

**Nova interface de relatórios** e acesso aos novos recursos de relatório:

<table>
<tr>
<th>Antes</th>
<th>Depois</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>Exibição global</strong> O permite medir o impacto das jornadas e deliveries em um período selecionado. Para obter mais métricas em tempo real, você pode acessar a variável <strong>Exibição ao vivo</strong>. Para cada canal de delivery que está sendo usado em suas jornadas (Email, SMS, Push), um <strong>seção dedicada</strong> está disponível no relatório para exibir métricas. Isso se aplica somente se você usar o pronto para uso <strong>Recursos de mensagens do Adobe Journey Optimizer</strong>. Entre em contato com a equipe de conta para obter mais informações.</p></td>
</tr>
</table>

Qualquer evolução para melhorar a experiência de relatórios ou para enriquecê-la após novas versões de recursos só estará disponível na nova interface de relatórios. Comece a usá-la para obter uma experiência mais completa do Adobe Journey Optimizer.

Obter o benefício de outros **Recursos do Adobe Journey Optimizer** e novos, como Controle de acesso em nível de campo e Controle de acesso em nível de objeto. Entre em contato com a equipe de conta para obter mais informações.

## Como atualizar meu ambiente Journey Orchestration?

1. Entre em contato com a equipe de conta para atualizar seu contrato com o Adobe sem custo.

1. Aguarde a equipe de engenharia concluir a alteração.

1. Atualize suas permissões usando perfis de produto do Journey Optimizer. Consulte esta [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=pt-BR).

1. Agora você tem acesso ao Adobe Journey Optimizer!

## Perguntas frequentes

## Preciso planejar alguma coisa para migrar do Journey Orchestration para o Adobe Journey Optimizer?

Não, não há migração, não há trabalho necessário de você, tempo de inatividade e nenhum investimento adicional. Você só precisa atualizar seu contrato com o Adobe e nós fazemos o resto. Entre em contato com seu representante de conta para obter instruções sobre como iniciar esse processo.

## Perderei algo depois da mudança?

Não, você manterá todos os objetos Journey Orchestration e Adobe Experience Platform existentes: esquemas, conjuntos de dados, jornadas, eventos, fontes de dados, ações. Nada será perdido, todas as jornadas ao vivo continuarão a funcionar sem interrupção.

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

### Ainda vejo Journey Orchestration no alternador de aplicativos, é normal?

![](../assets/migration-ajo-9.png)

Sim, é normal. Você manterá o acesso ao Journey Orchestration por um mês após a atualização. Isso dará tempo suficiente para atualizar todas as permissões de usuários e se familiarizar com o Adobe Journey Optimizer. Após um mês, o acesso será removido.

### O que acontece se eu usar o Journey Orchestration com o Adobe Campaign Standard hoje?

Ao mudar para o Adobe Journey Optimizer, você ainda poderá usar a integração entre o Jornada e o Adobe Campaign Standard, criando sua jornada de cliente no Adobe Journey Optimizer e permitindo que o Adobe Campaign Standard envie o delivery.

No entanto, devido à forma como a pilha de relatórios do Adobe Journey Optimizer funciona, os relatórios não combinarão dados de Jornada e Campaign Standard. As informações de jornada estarão disponíveis nos relatórios do Adobe Journey Optimizer e nas informações de delivery no Adobe Campaign Standard. Uma configuração do Experience Platform pode ser feita para trazer de volta os dados do Adobe Campaign Standard para o Adobe Experience Platform, tornando-os disponíveis para o Customer Journey Analytics ([saiba mais](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html)) ou outras ferramentas de relatório de terceiros, como o Tableau ou Power BI.

Os relatórios do Adobe Journey Optimizer operam melhor ao usar os recursos de mensagens prontos para uso do Adobe Journey Optimizer (disponíveis em ofertas dedicadas do Adobe Journey Optimizer). Para obter mais informações sobre como as Mensagens podem ser criadas na tela de jornada, consulte esta seção [página](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

Entre em contato com a equipe de conta para obter mais informações.