---
product: adobe campaign
title: Sobre a configuração de ação personalizada
description: Saiba como configurar uma ação personalizada
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 11%

---

# Sobre a configuração de ação personalizada {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


Se você estiver usando um sistema de terceiros para enviar mensagens ou se quiser que o [!DNL Journey Orchestration] envie chamadas de API para um sistema de terceiros, é aqui que você configura sua conexão com o [!DNL Journey Orchestration]. A ação personalizada definida pelos usuários técnicos estará então disponível na paleta esquerda da sua jornada, na categoria **[!UICONTROL Action]** (consulte [esta página](../building-journeys/about-action-activities.md). Estes são alguns exemplos de sistemas aos quais você pode se conectar com ações personalizadas: Epsilon, Facebook, Adobe.io, Firebase etc.

As limitações estão listadas em [esta página](../about/limitations.md).

Em parâmetros de ação personalizados, você pode passar uma coleção simples, bem como uma coleção de objetos. Quanto às limitações, consulte [esta página](../usecase/collections.md#limitations). Observe também que os parâmetros têm um formato esperado (por exemplo: sequência, decimal etc.). Você deve ter cuidado para respeitar esses formatos esperados. Consulte este [caso de uso](../usecase/collections.md).

Estas são as principais etapas necessárias para configurar uma ação personalizada:

1. Na lista **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]** para criar uma nova ação. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/custom2.png)

1. Digite um nome para a ação.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição à ação. Esta etapa é opcional.
1. O número de jornadas que usam esta ação é exibido no campo **[!UICONTROL Used in]**. Você pode clicar no botão **[!UICONTROL View journeys]** para exibir a lista de jornadas usando esta ação.
1. Defina os diferentes parâmetros **[!UICONTROL URL Configuration]**. Consulte [esta página](../action/url-configuration.md).
1. Configure a seção **[!UICONTROL Authentication]**. Essa configuração é a mesma das fontes de dados.  Consulte [esta seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina o **[!UICONTROL Action parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Clique em **[!UICONTROL Save]**.

   A ação personalizada agora está configurada e pronta para ser usada em suas jornadas. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando uma ação personalizada é usada em uma jornada, a maioria dos parâmetros é somente leitura. Você só pode modificar os campos **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e a seção **[!UICONTROL Authentication]**.
