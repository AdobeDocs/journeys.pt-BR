---
title: Sobre a configuração de ação personalizada
description: Saiba como configurar uma ação personalizada
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 9fc7f0664afa19e3debe2ad4f37d6b794da0ed1f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# Sobre a configuração de ação personalizada {#concept_sxy_bzs_dgb}

Se você estiver usando um sistema de terceiros para enviar mensagens ou se quiser [!DNL Journey Orchestration] enviar chamadas de API para um sistema de terceiros, é aqui que você configura a conexão com [!DNL Journey Orchestration]. A ação personalizada definida pelos usuários técnicos estará disponível na paleta esquerda de sua jornada, na **[!UICONTROL Action]** categoria (consulte [esta página](../building-journeys/about-action-activities.md)). Estes são alguns exemplos de sistemas aos quais você pode se conectar com ações personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.
As limitações estão listadas [nesta página](../about/limitations.md).

Estas são as principais etapas necessárias para configurar uma ação personalizada:

1. Na **[!UICONTROL Actions]** lista, clique em **[!UICONTROL Add]** para criar uma nova ação. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/custom2.png)

1. Insira um nome para a sua ação.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição à sua ação. Esta etapa é opcional.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. Consulte [esta página](../action/url-configuration.md).
1. Configure a **[!UICONTROL Authentication]** seção. Essa configuração é a mesma para fontes de dados.  Consulte [esta seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina o **[!UICONTROL Message parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Clique em **[!UICONTROL Save]**.

   A ação personalizada agora está configurada e pronta para ser usada em suas viagens. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando uma ação personalizada é usada em uma jornada, a maioria dos parâmetros são somente leitura. Você só pode modificar os campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e a **[!UICONTROL Authentication]** seção.
