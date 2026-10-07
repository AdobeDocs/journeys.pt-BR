---
product: adobe campaign
title: Sobre ações
description: Saiba como configurar uma ação
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 86%
---
# Sobre ações {#about_actions}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


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

