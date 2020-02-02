---
title: Sobre fontes de dados
description: 'Saiba como configurar uma fonte de dados '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# Sobre fontes de dados {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Sobre fontes de dados&quot;
>abstract=&quot;A configuração da fonte de dados é sempre executada por um usuário técnico. A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas viagens, para: definição de condição, parâmetro e dados de personalização em ações, definição de espera personalizada, definição de fuso horário personalizado.&quot;

A configuração da fonte de dados é sempre executada por um usuário **** técnico.

A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas viagens, para:

* definição de condição
* parâmetros e dados de personalização em ações
* definição de espera personalizada
* definição de fuso horário personalizado

Essa configuração não é necessária se suas viagens só potencializarem os dados locais provenientes de uma carga de eventos. Por exemplo, se sua jornada for composta de um evento seguido de uma atividade de email que usa somente dados do evento, não será necessário configurar uma fonte de dados.

Há dois tipos de fontes de dados:

* A fonte de dados pré-configurada da plataforma de experiência que define a conexão com o Serviço de perfil do cliente em tempo real. Esta é uma fonte de dados integrada. Consulte [](../datasource/adobe-experience-platform-data-source.md).
* As fontes de dados externas que permitem definir uma conexão com sistemas externos. Estes são os que você pode criar. Consulte [](../datasource/external-data-sources.md).

Para cada fonte de dados, você define as informações a serem recuperadas usando grupos de campos. Consulte [](../datasource/field-groups.md).

Estas são as etapas principais de configuração da fonte de dados:

1. No menu superior, clique na **[!UICONTROL Data Sources]**guia.

   A lista de fontes de dados é exibida. Consulte [](../about/user-interface.md) para obter mais informações sobre a interface.

   ![](../assets/journey18.png)

1. Em seguida, é possível adicionar grupos de campos à fonte de dados integrada (consulte [](../datasource/adobe-experience-platform-data-source.md)) ou criar uma nova fonte de dados externa (consulte [](../datasource/external-data-sources.md)) e grupos de campos associados (consulte [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clique em **[!UICONTROL Save]**.

   A fonte de dados agora está configurada e pronta para ser usada em suas viagens.
