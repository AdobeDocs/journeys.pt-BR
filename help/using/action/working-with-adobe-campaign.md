---
product: adobe campaign
solution: Journey Orchestration
title: Trabalhar com o Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
translation-type: tm+mt
source-git-commit: 723c30865a5039bd68a8ac2e45d4c87a760e694d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---


# Trabalhar com o Adobe Campaign {#using_adobe_campaign_standard}

Você pode enviar emails, notificações por push e SMS usando os recursos de Mensagens Transacionais da Adobe Campaign Standard.

[!DNL Journey Orchestration] vem com uma ação pronta para uso que permite a conexão com o Adobe Campaign Standard.

O mensagen transacional Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for publicada, ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas seu evento associado não for, ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

>[!NOTE]
>
>O Adobe Campaign Standard Transactional Messaging tem uma escala máxima de 50.000 mensagens por hora em canais para uma determinada instância. Para reduzir o risco de sobrecarga, recomendamos que você configure uma **regra de limite** para a integração com o Campaign Standard.
>
>Leia mais sobre SLAs de mensagens transacionais em [Descrição do Produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Estas são as etapas para configurá-lo:

1. Na lista **[!UICONTROL Actions]**, clique na ação incorporada **[!UICONTROL AdobeCampaignStandard]**. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/actioncampaign.png)

1. Copie o URL da instância do Adobe Campaign Standard e cole-o no campo **[!UICONTROL URL]**.

1. Clique em **[!UICONTROL Test the instance URL]** para testar a validade da instância.

   >[!NOTE]
   >
   >Este teste verifica se:
   >
   >O host é &quot;.campanha.adobe.com&quot;, &quot;.campanha-sandbox.adobe.com&quot; ou &quot;campanha-demo.adobe.com&quot;
   >
   >Os start de URL com https,
   >
   >O ORG associado a esta instância do Adobe Campaign Standard é o mesmo que o Journey Orchestration ORG.

Ao projetar sua jornada, três ações estarão disponíveis na categoria **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de ações do Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Os** eventos de reações também permitirão que você reaja aos cliques em mensagens, às aberturas, etc. (consulte [eventos de reação](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se você estiver usando um sistema de terceiros para enviar mensagens, precisará adicionar e configurar uma ação personalizada. Consulte [Sobre a configuração de ação personalizada](../action/about-custom-action-configuration.md).
