---
product: adobe campaign
title: Eventos de reações
description: Saiba mais sobre eventos de reação
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 2%

---

# Eventos de reação {#section_dhx_gss_dgb}

Entre as diferentes atividades de evento disponíveis na paleta, você encontrará o incorporado **[!UICONTROL Reactions]** evento. Essa atividade permite que você reaja aos dados de rastreamento relacionados a uma mensagem enviada com atividades de email, SMS ou push na mesma jornada. Essas informações vêm de mensagens transacionais no Adobe Campaign Standard. Capturamos essas informações em tempo real no momento em que são compartilhadas com a Adobe Experience Platform. Para notificações por push, você pode reagir a mensagens clicadas, enviadas ou com falha. Para mensagens SMS, você pode reagir a mensagens enviadas ou com falha. Para emails, você pode reagir a mensagens clicadas, enviadas, abertas ou com falha.

Você também pode usar esse mecanismo para executar uma ação quando não houver reação às suas mensagens. Para fazer isso, crie um segundo caminho paralelo à atividade de reação e adicione uma atividade de espera. Se não houver reação durante o período definido na atividade de espera, o segundo caminho será escolhido. Você pode optar por enviar, por exemplo, uma mensagem de acompanhamento.

Observe que você só pode usar uma atividade de reação na tela se houver uma atividade de email, push ou SMS antes.

Consulte [Sobre as atividades de ação](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Estas são as diferentes etapas para configurar os eventos de reação:

1. Adicionar um **[!UICONTROL Label]** à reação. Esta etapa é opcional.
1. Na lista suspensa, selecione a atividade de ação à qual deseja reagir. Você pode selecionar qualquer atividade de ação posicionada nas etapas anteriores do caminho.
1. Dependendo da ação selecionada (um email, SMS ou uma notificação por push), escolha a que você deseja reagir.
1. Você pode definir um tempo limite de evento (entre 40 segundos e 30 dias) e um caminho de tempo limite. Isso criará um segundo caminho para indivíduos que não reagiram dentro da duração definida. Ao testar uma jornada que usa um evento de reação, o modo de teste **[!UICONTROL Wait time]** padrão e o valor mínimo é de 40 segundos. Consulte [esta seção](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Os eventos de reação funcionam com o Adobe Campaign Standard, seja ele implantado em servidores AWS ou Azure.
>
>Os eventos de reação não podem rastrear emails, SMS ou ações de push que ocorrem em uma jornada diferente.
>
>Eventos de reação rastreiam cliques em links do tipo &quot;rastreado&quot; (consulte esta [página](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Links de unsubscription e mirror pages não são considerados.

>[!IMPORTANT]
>
>Clientes de email, como o Gmail, permitem o bloqueio de imagens. As aberturas de emails são rastreadas usando uma imagem de 0 pixel incluída no email. Se as imagens forem bloqueadas, as aberturas de email não serão consideradas.
