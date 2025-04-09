---
product: adobe campaign
title: Introdução
description: Descubra as etapas principais para configurar o Journey Orchestration e criar sua primeira jornada.
feature: Journeys
role: User
level: Beginner
exl-id: fe7bb5fe-7b5e-46da-8ef8-ae9401522c03
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 88%

---

# Introdução{#concept_y4b_4qt_52b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._




No [!DNL Journey Orchestration] existem dois tipos de usuários, cada um deles com tarefas específicas: o **usuário técnico** e o **usuário empresarial**. O acesso do usuário é gerenciado por perfis de produtos e direitos. Consulte [esta página](../about/access-management.md) para aprender a configurar o acesso do usuário.

Estas são as etapas principais para configurar e utilizar o [!DNL Journey Orchestration]:

1. **Configurar um evento**

   É necessário definir as informações esperadas e como processá-las. Esta configuração é obrigatória. Esta etapa é executada por um **usuário técnico**.

   Para obter mais informações, consulte [esta página](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurar a fonte de dados**

   É necessário definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas, por exemplo, em suas condições. Uma fonte de dados integrada da Adobe Experience Platform também é configurada no momento do provisionamento. Esta etapa não é necessária se você usar somente os dados dos eventos em sua jornada. Esta etapa é executada por um **usuário técnico**.

   Para obter mais informações, consulte [esta página](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurar uma ação**

   Se você estiver usando um sistema de terceiros para enviar mensagens, será necessário configurar a conexão com o [!DNL Journey Orchestration]. Consulte [esta página](../action/about-custom-action-configuration.md).

   Se você está usando o Adobe Campaign Standard para enviar mensagens, é necessário configurar a ação integrada. Consulte [esta página](../action/working-with-adobe-campaign.md).

   Estas etapas são executadas por um **usuário técnico**.

   ![](../assets/custom2.png)

1. **Projetar a jornada**

   Combine diferentes atividades de evento, orquestração e ação para criar cenários de canais em várias etapas. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte [esta página](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testar e publicar a jornada**

   Você precisa validar e ativar a jornada. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte as páginas [Teste da jornada](../building-journeys/testing-the-journey.md) e [Publicação da jornada](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorar a jornada**

   Use as ferramentas de relatórios exclusivos para medir a eficiência da sua jornada. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte [esta página](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)
