---
product: adobe campaign
title: Sobre a configuração de ação personalizada
description: Saiba como configurar uma ação personalizada
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
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
source-wordcount: '358'
ht-degree: 25%
---
# Sobre a configuração de ação personalizada {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


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
