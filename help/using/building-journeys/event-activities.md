---
title: Atividades de eventos
description: Saiba mais sobre atividades de eventos
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Atividades de eventos {#concept_rws_1rt_52b}

Os eventos configurados pelo usuário técnico (consulte [](../event/about-events.md) são exibidos na primeira categoria da paleta, no lado esquerdo da tela.

![](../assets/journey43.png)

Sempre inicie sua jornada arrastando e soltando uma atividade de evento. Você também pode clicar duas vezes nele.

![](../assets/journey44.png)

Quando você clica na atividade do evento na tela, o painel de configuração da atividade é exibido. Por padrão, quando você usa o mesmo evento várias vezes, um número incrementado é adicionado ao nome do evento na tela. Além disso, você pode usar o **[!UICONTROL Label]**campo para adicionar um sufixo ao nome do evento que aparecerá sob sua atividade na tela. Isso é útil para identificar seus eventos na tela, especialmente se você usar o mesmo evento várias vezes. Também facilitará a depuração em caso de erros e facilitará a leitura dos relatórios.

![](../assets/journey33.png)

## Eventos gerais {#section_ofg_jss_dgb}

Para esse tipo de evento, você só pode adicionar um rótulo e uma descrição. O restante da configuração não pode ser editado. Foi executado pelo usuário técnico. Consulte [](../event/about-events.md).

## Eventos de reação {#section_dhx_gss_dgb}

Entre as diferentes atividades de evento disponíveis na paleta, você encontrará o evento **Reações** incorporado. Esta atividade permite que você reaja aos dados de rastreamento relacionados a uma mensagem enviada com email, SMS ou atividades de push na mesma jornada. Essas informações vêm de mensagens transacionais no Adobe Campaign Standard. Captamos essas informações em tempo real no momento em que são compartilhadas com a Plataforma de dados. Para notificações por push, você pode reagir a mensagens clicadas, enviadas ou com falha. Para mensagens SMS, você pode reagir a mensagens enviadas ou com falha. Para emails, você pode reagir a mensagens clicadas, enviadas, abertas ou com falha.

Você também pode usar esse mecanismo para executar uma ação quando não houver reação às suas mensagens. Para fazer isso, crie um segundo caminho paralelo à atividade de reação e adicione uma atividade de espera. Se não houver reação durante o período definido na atividade de espera, o segundo caminho será escolhido. Você pode optar por enviar, por exemplo, uma mensagem de acompanhamento.

Observe que você só pode usar uma atividade de reação na tela se houver uma atividade de email, push ou SMS antes.

Consulte [](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estas são as diferentes etapas para configurar os eventos de reação:

1. Adicione um comentário **[!UICONTROL Label]**à reação. Esta etapa é opcional.
1. Na lista suspensa, selecione a atividade de ação à qual deseja reagir. É possível selecionar qualquer atividade de ação posicionada nas etapas anteriores do caminho.
1. Dependendo da ação selecionada (um email, SMS ou uma notificação por push), escolha o que deseja reagir.
1. É possível definir uma condição como uma etapa opcional. Por exemplo, após uma ação de email, você pode decidir criar dois caminhos, um com um evento de reação para rastrear cliques somente para clientes VIP e outro com um evento de reação para rastrear cliques executados por mulheres.

>[!NOTE]
>
>Os eventos de reação não podem rastrear ações de email, SMS ou push que ocorrem em uma jornada diferente.
>
>Os eventos de reação rastreiam cliques em links do tipo &quot;acompanhados&quot; (consulte esta [página](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Os links de página de cancelamento de assinatura e espelhamento não são considerados.

>[!CAUTION]
>
>Clientes de email como o Gmail permitem bloqueio de imagem. Os e-mails abertos são rastreados usando uma imagem de 0 pixels incluída no e-mail. Se as imagens estiverem bloqueadas, a abertura do email não será levada em conta.

## Uso avançado: eventos com uma espera em paralelo{#section_vxv_h25_pgb}

**Como você pode ouvir um evento somente durante um determinado período?**

Uma atividade de evento posicionada na jornada escuta os eventos indefinidamente. Para ouvir um evento somente durante um determinado tempo, é necessário adicionar uma atividade de espera paralela ao caminho do evento. A jornada ouvirá o evento durante o tempo especificado na atividade de espera. Se um evento for recebido durante esse período, a pessoa continuará no caminho do evento. Caso contrário, o cliente fluirá para o caminho de espera.

Por exemplo, você enviou um primeiro push de boas-vindas para um cliente e deseja enviar um push de desconto de refeição somente se o cliente entrar no restaurante dentro das próximas 6 horas. Para fazer isso, você criará um segundo caminho (paralelo ao evento de restaurante um) com uma atividade de espera de 6 horas. Se o evento do restaurante for recebido menos de 6 horas após o push de boas-vindas, a atividade de push de desconto para refeições será enviada. Se nenhum evento de restaurante for recebido dentro das próximas 6 horas, a pessoa percorre o caminho de espera.

![](../assets/journeyuc2_31.png)
