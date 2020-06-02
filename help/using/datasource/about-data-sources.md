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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 88%

---


# Sobre fontes de dados {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Sobre fontes de dados"
>abstract="A configuração da fonte de dados é sempre executada por um usuário técnico. A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas viagens, para: definição de condição, parâmetro e dados de personalização em ações, definição de espera personalizada, definição de fuso horário."

A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas, para:

* [definição de condição](../building-journeys/condition-activity.md)
* parâmetros e dados de personalização em [ações](../action/action.md)
* [definição de espera personalizada](../building-journeys/wait-activity.md#custom)
* [definição de fuso horário](../building-journeys/timezone-management.md)

Essa configuração não é necessária se suas jornadas só usarem os dados locais provenientes de uma carga útil do evento. Por exemplo, se sua jornada for composta por um evento seguido por uma atividade de email que usa somente os dados do evento, não será necessário configurar uma fonte de dados.

Há dois tipos de fontes de dados:

* A fonte de dados pré-configurada da Experience Platform que define a conexão com o Serviço de Perfil do cliente em tempo real. Essa fonte de dados é integrada. Consulte [](../datasource/adobe-experience-platform-data-source.md).
* As fontes de dados externas que permitem definir uma conexão com sistemas externos. Essas são as que você pode criar. Consulte [](../datasource/external-data-sources.md).

Para cada fonte de dados, você define as informações que serão recuperadas usando grupos de campos. Grupos de campos são conjuntos de campos que podem ser recuperados de uma fonte de dados. Consulte [](../datasource/field-groups.md).

Para obter mais informações sobre como configurar uma Fonte de Dados da Experience Platform e uma fonte de dados externa e como localizar e usar dados em uma jornada, assista a este [tutorial em vídeo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Estas são as etapas principais de configuração da fonte de dados:

>[!NOTE]
>
>A configuração da fonte de dados é sempre executada por um **usuário técnico**.

1. No menu superior, clique na guia **[!UICONTROL Data Sources]**.

   A lista das fontes de dados é exibida. Consulte [](../about/user-interface.md) para obter mais informações sobre a interface.

   ![](../assets/journey18.png)

1. Você pode adicionar grupos de campos à fonte de dados integrada (consulte [](../datasource/adobe-experience-platform-data-source.md)) ou criar uma nova fonte de dados externa (consulte [](../datasource/external-data-sources.md)) e grupos de campos associados (consulte [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clique em **[!UICONTROL Save]**.

   A fonte de dados agora está configurada e pronta para ser usada em suas jornadas.
