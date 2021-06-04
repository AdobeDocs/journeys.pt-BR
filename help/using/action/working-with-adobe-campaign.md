---
product: adobe campaign
title: Trabalhar com o Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Trabalhar com o Adobe Campaign Standard {#using_adobe_campaign_standard}

Você pode enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais da Adobe Campaign Standard.

[!DNL Journey Orchestration] O vem com uma ação pronta para uso que permite a conexão com o Adobe Campaign Standard.

A mensagem transacional do Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for , ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas o evento associado não for , ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

>[!NOTE]
>
>Uma regra de limitação de 13 chamadas por segundo é definida automaticamente para ações do Adobe Campaign Standard assim que a integração do Adobe Campaign Standard é configurada. Isso corresponde à escala oficial do Adobe Campaign Standard Transactional Messaging.
>
>Leia mais sobre SLAs de mensagens transacionais em [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Estas são as etapas para configurá-lo:

1. Na lista **[!UICONTROL Actions]**, clique na ação **[!UICONTROL AdobeCampaignStandard]** incorporada. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/actioncampaign.png)

1. Copie o URL da instância do Adobe Campaign Standard e cole-o no campo **[!UICONTROL URL]** .

1. Clique em **[!UICONTROL Test the instance URL]** para testar a validade da instância.

   >[!NOTE]
   >
   >Este teste verifica se:
   >
   >O host é &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; ou &quot;.adls.adobe.com&quot;.
   >
   >O URL começa com https,
   >
   >O ORG associado a esta instância do Adobe Campaign Standard é o mesmo que o Journey Orchestration ORG.

Ao projetar a jornada, três ações estarão disponíveis na categoria **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de ações do Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Os** eventos de Reações também permitirão reagir a cliques em mensagens, aberturas, etc. (consulte [Eventos de reação](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se estiver usando um sistema de terceiros para enviar mensagens, será necessário adicionar e configurar uma ação personalizada. Consulte [Sobre a configuração de ação personalizada](../action/about-custom-action-configuration.md).
