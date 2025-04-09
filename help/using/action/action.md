---
product: adobe campaign
title: Sobre ações
description: Saiba como configurar uma ação
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 72%

---

# Sobre ações {#about_actions}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Sobre ações"
>abstract="É aqui que você define a conexão com o sistema que enviará mensagens. As ações definidas aqui estarão disponíveis na paleta esquerda da sua jornada, na categoria Ação. "

As ações são conexões através das quais você fornece experiências personalizadas em tempo real para clientes, como notificações por push, email, SMS ou qualquer outro meio de engajamento digital usado em sua empresa.

As ações personalizadas permitem configurar a conexão de um sistema de terceiros para enviar mensagens ou chamadas de API. Uma ação pode ser configurada com qualquer serviço de qualquer provedor que possa ser chamado por meio de uma REST API com conteúdo formatado em JSON.

As ações estão disponíveis na paleta esquerda da sua jornada, na categoria **[!UICONTROL Action]**. Consulte [esta página](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>A configuração de ações personalizadas é sempre executada por um **usuário técnico**.

Na lista de **Ações**, você pode pressionar C para criar uma nova jornada, ação, fonte de dados ou evento. Para obter mais informações sobre atalhos no [!DNL Journey Orchestration], consulte [esta seção](../about/user-interface.md#section_ksq_zr1_ffb).

Para visualizar a lista de ações ou configurar uma nova ação, clique em **[!UICONTROL Actions]** nos menus superiores. A lista de ações é exibida. Consulte [esta página](../about/user-interface.md) para obter mais informações sobre a interface.

![](../assets/custom1.png)

Se você tiver o Adobe Campaign Standard, precisará configurar a ação pronta para enviar emails, notificações por push e SMS usando os recursos de mensagens transacionais do Adobe Campaign Standard. Consulte [esta página](../action/working-with-adobe-campaign.md).

Se você tiver o Adobe Campaign v7 ou v8, uma integração estará disponível mediante solicitação. Consulte [esta página](../action/acc-action.md).

Se você estiver usando um sistema de terceiros para enviar mensagens como Epsilon, Facebook, Adobe.io, Firebase, etc., é necessário adicionar e configurar uma ação personalizada. Consulte [esta página](../action/about-custom-action-configuration.md).

