---
title: Introdução
description: Descubra as etapas principais para configurar o Journey Orchestration e construir sua primeira jornada.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 38b555e19b9c3a0757962cbedbf3587e64f69add
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 95%

---


# Introdução{#concept_y4b_4qt_52b}

No [!DNL Journey Orchestration] existem dois tipos de usuários, cada um deles com tarefas específicas: o **usuário técnico** e o **usuário empresarial**. O acesso do usuário é gerenciado por perfis de produtos e direitos. Consulte [](../about/access-management.md) para saber como configurar o acesso do usuário.

Estas são as etapas principais para configurar e utilizar o [!DNL Journey Orchestration]:

1. **Configurar um evento**

   É necessário definir as informações esperadas e como processá-las. Esta configuração é obrigatória. Esta etapa é executada por um **usuário técnico**.

   Para obter mais informações, consulte [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurar a fonte de dados**

   É necessário definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas, por exemplo, em suas condições. Uma fonte de dados integrada da Adobe Experience Platform também é configurada no momento do provisionamento. Esta etapa não é necessária se você usar somente os dados dos eventos em sua jornada. Esta etapa é executada por um **usuário técnico**.

   Para obter mais informações, consulte [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurar uma ação**

   Se você estiver usando um sistema de terceiros para enviar mensagens, será necessário configurar a conexão com o [!DNL Journey Orchestration]. Consulte [](../action/about-custom-action-configuration.md).

   Se você estiver usando o Adobe Campaign Standard para enviar mensagens, é necessário configurar a ação integrada. Consulte [](../action/working-with-adobe-campaign.md).

   Estas etapas são executadas por um **usuário técnico**.

   ![](../assets/custom2.png)

1. **Projetar a jornada**

   Combine diferentes atividades de evento, orquestração e ação para criar cenários de canais em várias etapas. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testar e publicar a jornada**

   Você precisa validar e ativar a jornada. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte [](../building-journeys/testing-the-journey.md) e [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorar a jornada**

   Use as ferramentas de relatórios exclusivos para medir a eficiência da sua jornada. Esta etapa é executada por um **usuário empresarial**.

   Para obter mais informações, consulte [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

