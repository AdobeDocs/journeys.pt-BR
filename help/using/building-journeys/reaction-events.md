---
title: eventos de reações
description: Saiba mais sobre eventos de reação
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
source-git-commit: 2b44cd9db7732c5e272b69e2583a5f81b4580d11
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# eventos de reação {#section_dhx_gss_dgb}

Entre as diferentes atividades de evento disponíveis na paleta, você encontrará o **[!UICONTROL Reactions]** evento integrado. Esta atividade permite que você reaja aos dados de rastreamento relacionados a uma mensagem enviada com atividades de email, SMS ou push na mesma jornada. Essas informações vêm de mensagens transacionais no Adobe Campaign Standard. Captamos essas informações em tempo real no momento em que são compartilhadas com a Adobe Experience Platform. Para notificações por push, você pode reagir a mensagens clicadas, enviadas ou com falha. Para mensagens SMS, você pode reagir a mensagens enviadas ou com falha. Para emails, você pode reagir a mensagens clicadas, enviadas, abertas ou com falha.

Você também pode usar esse mecanismo para executar uma ação quando não houver reação às suas mensagens. Para fazer isso, crie um segundo caminho paralelo à atividade de reação e adicione uma atividade de espera. Se não houver reação durante o período definido na atividade de espera, o segundo caminho será escolhido. Você pode optar por enviar, por exemplo, uma mensagem de acompanhamento.

Observe que você só pode usar uma atividade de reação na tela se houver uma atividade de email, push ou SMS antes.

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estas são as diferentes etapas para configurar os eventos de reação:

1. Adicione um comentário **[!UICONTROL Label]** à reação. Esta etapa é opcional.
1. Na lista suspensa, selecione a atividade de ação à qual deseja reagir. É possível selecionar qualquer atividade de ação posicionada nas etapas anteriores do caminho.
1. Dependendo da ação selecionada (um email, SMS ou uma notificação por push), escolha o que deseja reagir.
1. É possível definir uma condição como uma etapa opcional. Por exemplo, após uma ação de email, você pode decidir criar dois caminhos, um com um evento de reação para rastrear cliques somente para clientes VIP e outro com um evento de reação para rastrear cliques executados por mulheres.

>[!NOTE]
>
>Os eventos de reação funcionam com o Adobe Campaign Standard, independentemente de ele estar implantado em servidores AWS ou Azure.
>
>Os eventos de reação não podem rastrear ações de email, SMS ou push que ocorrem em uma jornada diferente.
>
>Os eventos de reação rastreiam cliques em links do tipo &quot;acompanhados&quot; (consulte esta [página](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Os links de Unsubscription e mirror page não são considerados.

>[!IMPORTANT]
>
>Clientes de email como o Gmail permitem bloqueio de imagem. Os e-mails abertos são rastreados usando uma imagem de 0 pixels incluída no e-mail. Se as imagens estiverem bloqueadas, as aberturas de e-mail não serão levadas em conta.
