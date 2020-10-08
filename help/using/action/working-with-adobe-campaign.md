---
title: Trabalhar com o Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 4%

---


# Trabalhar com o Adobe Campaign {#using_adobe_campaign_standard}

Você pode enviar emails, notificações por push e SMS usando os recursos de Mensagens Transacionais da Adobe Campaign Standard.

[!DNL Journey Orchestration] vem com uma ação pronta para uso que permite a conexão com o Adobe Campaign Standard.

O mensagen transacional Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for publicada, ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas seu evento associado não for, ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

>[!NOTE]
>
>Para evitar sobrecarregar o Adobe Campaign Standard Transactional Messaging, é recomendável configurar uma regra **de** limite para a integração com o Campaign Standard.
>
>Leia mais sobre SLAs de mensagens transacionais na Descrição [do produto](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard.

Estas são as etapas para configurá-lo:

1. Na **[!UICONTROL Actions]** lista, clique na ação integrada **[!UICONTROL AdobeCampaignStandard]** . O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/actioncampaign.png)

1. Copie o URL da instância do Adobe Campaign Standard e cole-o no **[!UICONTROL URL]** campo.

1. Clique no link **[!UICONTROL Test the instance URL]** para testar a validade da instância.

   >[!NOTE]
   >
   >Este teste verifica se:
   >
   >O host é &quot;.campanha.adobe.com&quot; ou &quot;.campanha-sandbox.adobe.com&quot;,
   >
   >Os start de URL com https,
   >
   >O ORG associado a esta instância do Adobe Campaign Standard é o mesmo que o Journey Orchestration ORG.

Ao projetar sua jornada, três ações estarão disponíveis na **[!UICONTROL Action]** categoria: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de ações](../building-journeys/using-adobe-campaign-actions.md)do Adobe Campaign). **O evento** Reações também permitirá que você reaja a cliques em mensagens, aberturas, etc. (consulte eventos [de reação](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se você estiver usando um sistema de terceiros para enviar mensagens, precisará adicionar e configurar uma ação personalizada. See [About custom action configuration](../action/about-custom-action-configuration.md).
