---
title: Sobre ações
description: Saiba como configurar uma ação
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 89%

---


# Sobre ações {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Sobre ações"
>abstract="É aqui que você define a conexão com o sistema que enviará mensagens. As ações definidas aqui estarão disponíveis na paleta esquerda da sua jornada, na categoria Ação. "

As ações são conexões através das quais você fornece experiências personalizadas em tempo real para clientes, como notificações por push, email, SMS ou qualquer outro meio de engajamento digital usado em sua empresa.

As ações personalizadas permitem configurar a conexão de um sistema de terceiros para enviar mensagens ou chamadas de API. Uma ação pode ser configurada com qualquer serviço de qualquer provedor que possa ser chamado por meio de uma REST API com uma carga útil formatada em JSON.

As ações estão disponíveis na paleta esquerda da sua jornada, na categoria (**[!UICONTROL Action]** consulte [](../building-journeys/about-action-activities.md) ).

>[!NOTE]
>
>A configuração de ações personalizadas é sempre executada por um **usuário técnico**.

Na lista de **Ações**, você pode pressionar C para criar uma nova jornada, ação, fonte de dados ou evento. For more information on shortcuts in [!DNL Journey Orchestration], see [](../about/user-interface.md#section_ksq_zr1_ffb).

Para visualizar a lista de ações ou configurar uma nova ação, clique em **[!UICONTROL Actions]** nos menus superiores. A lista de ações é exibida. Consulte [](../about/user-interface.md) para obter mais informações sobre a interface.

![](../assets/custom1.png)

Se você tiver o Adobe Campaign Standard, precisará configurar a ação pronta para enviar emails, notificações por push e SMS usando os recursos de mensagens transacionais do Adobe Campaign Standard. Consulte [](../action/working-with-adobe-campaign.md).

Se você estiver usando um sistema de terceiros para enviar mensagens como Epsilon, Facebook, Adobe.io, Firebase, etc., é necessário adicionar e configurar uma ação personalizada. Consulte [](../action/about-custom-action-configuration.md).

For more information on how to configure an Action for [!DNL Journey Orchestration] and how to use it in a journey, watch this [video tutorial](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html).
