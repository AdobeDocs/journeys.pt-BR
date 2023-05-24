---
product: adobe campaign
title: Sobre a configuração de ação personalizada
description: Saiba como configurar uma ação personalizada
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# Sobre a configuração de ação personalizada {#concept_sxy_bzs_dgb}

Se você estiver usando um sistema de terceiros para enviar mensagens ou se desejar [!DNL Journey Orchestration] para enviar chamadas de API para um sistema de terceiros, configure a conexão com [!DNL Journey Orchestration]. A ação personalizada definida pelos usuários técnicos estará disponível na paleta esquerda da jornada, no **[!UICONTROL Action]** categoria (consulte [esta página](../building-journeys/about-action-activities.md). Estes são alguns exemplos de sistemas aos quais você pode se conectar com ações personalizadas: Epsilon, Facebook, Adobe.io, Firebase etc.

As limitações estão listadas em [esta página](../about/limitations.md).

Em parâmetros de ação personalizados, você pode passar uma coleção simples, bem como uma coleção de objetos. Quanto às limitações, consulte [esta página](../usecase/collections.md#limitations). Observe também que os parâmetros têm um formato esperado (por exemplo: sequência, decimal etc.). Você deve ter cuidado para respeitar esses formatos esperados. Consulte esta [caso de uso](../usecase/collections.md).

Estas são as principais etapas necessárias para configurar uma ação personalizada:

1. No **[!UICONTROL Actions]** clique em **[!UICONTROL Add]** para criar uma nova ação. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/custom2.png)

1. Digite um nome para a ação.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição à ação. Esta etapa é opcional.
1. O número de jornadas que usam esta ação é exibido no **[!UICONTROL Used in]** campo. Você pode clicar no link **[!UICONTROL View journeys]** botão para exibir a lista de jornadas usando esta ação.
1. Definir o diferente **[!UICONTROL URL Configuration]** parâmetros. Consulte [esta página](../action/url-configuration.md).
1. Configure o **[!UICONTROL Authentication]** seção. Essa configuração é a mesma das fontes de dados.  Consulte [esta seção](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Defina o **[!UICONTROL Action parameters]**. Consulte [esta página](../action/defining-the-message-parameters.md).
1. Clique em **[!UICONTROL Save]**.

   A ação personalizada agora está configurada e pronta para ser usada em suas jornadas. Consulte [esta página](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando uma ação personalizada é usada em uma jornada, a maioria dos parâmetros é somente leitura. Você só pode modificar a variável **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e os **[!UICONTROL Authentication]** seção.
