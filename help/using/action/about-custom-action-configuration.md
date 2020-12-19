---
product: adobe campaign
solution: Journey Orchestration
title: Sobre a configuração de ação personalizada
description: Saiba como configurar uma ação personalizada
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# Sobre a configuração de ação personalizada {#concept_sxy_bzs_dgb}

Se você estiver usando um sistema de terceiros para enviar mensagens ou se quiser que [!DNL Journey Orchestration] envie chamadas de API para um sistema de terceiros, é aqui que você configura sua conexão com [!DNL Journey Orchestration]. A ação personalizada definida pelos usuários técnicos estará disponível na paleta esquerda de sua jornada, na categoria **[!UICONTROL Action]** (consulte [esta página](../building-journeys/about-action-activities.md). Estes são alguns exemplos de sistemas aos quais você pode se conectar com ações personalizadas: Epsilon, Facebook, Adobe.io, Firebase, etc.
As limitações estão listadas em [esta página](../about/limitations.md).

Estas são as principais etapas necessárias para configurar uma ação personalizada:

1. Na lista **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]** para criar uma nova ação. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/custom2.png)

1. Insira um nome para a sua ação.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição à sua ação. Esta etapa é opcional.
1. O número de viagens que usam essa ação é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no botão **[!UICONTROL View journeys]** para exibir a lista de viagens usando esta ação.
1. Defina os diferentes parâmetros **[!UICONTROL URL Configuration]**. Consulte [esta página](../action/url-configuration.md).
1. Configure a seção **[!UICONTROL Authentication]**. Essa configuração é a mesma para fontes de dados.  Consulte [esta seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina **[!UICONTROL Message parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Clique em **[!UICONTROL Save]**.

   A ação personalizada agora está configurada e pronta para ser usada em suas viagens. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando uma ação personalizada é usada em uma jornada, a maioria dos parâmetros são somente leitura. Você só pode modificar os campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e **[!UICONTROL Authentication]**.
