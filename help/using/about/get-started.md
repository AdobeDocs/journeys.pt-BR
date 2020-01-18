---
title: Introdução
description: Comece com a Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Introdução{#concept_y4b_4qt_52b}

No Journey Orchestration, existem dois tipos de usuários, cada um deles executando tarefas específicas: o usuário **** técnico e o usuário **da** empresa. O acesso do usuário é gerenciado por meio de perfis de produtos e direitos. Consulte [](../about/access-management.md) para saber como configurar o acesso do usuário.

Estas são as etapas principais para configurar e usar o Journey Orchestration:

1. **Configurar um evento**

   É necessário definir as informações esperadas e como processá-las. Essa configuração é obrigatória. Esta etapa é executada por um usuário **** técnico.

   Para obter mais informações, consulte [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurar a fonte de dados**

   É necessário definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas viagens, por exemplo, em suas condições. Uma fonte de dados integrada da plataforma Experience também é configurada no momento do provisionamento. Esta etapa não é necessária se você só aproveitar os dados dos eventos em sua jornada. Esta etapa é executada por um usuário **** técnico.

   Para obter mais informações, consulte [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurar uma ação**

   Se você estiver usando um sistema de terceiros para enviar suas mensagens, precisará configurar sua conexão com o Journey Orchestration. Consulte [](../action/about-custom-action-configuration.md).

   Se você estiver usando o Adobe Campaign Standard para enviar mensagens, precisará configurar a ação integrada. Consulte [](../action/working-with-adobe-campaign.md).

   Essas etapas são executadas por um usuário **** técnico.

   ![](../assets/custom2.png)

1. **Projete sua jornada**

   Combine as diferentes atividades de evento, orquestração e ação para criar seus cenários multicanal. Esta etapa é executada por um usuário **** comercial.

   Para obter mais informações, consulte [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testar e publicar a viagem**

   Você precisa validar e ativar a jornada. Esta etapa é executada por um usuário **** comercial.

   For more on this, see [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitore sua jornada**

   Use as ferramentas de relatório dedicadas para medir a eficácia de sua jornada. Esta etapa é executada por um usuário **** comercial.

   Para obter mais informações, consulte [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

