---
product: adobe campaign
title: Sobre fontes de dados
description: 'Saiba como configurar uma fonte de dados '
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 79%

---

# Sobre fontes de dados {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Sobre fontes de dados"
>abstract="A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas."

A configuração da fonte de dados permite definir uma conexão com um sistema para recuperar informações adicionais que serão usadas em suas jornadas, para:

* [definição de condição](../building-journeys/condition-activity.md)
* parâmetros e dados de personalização em [ações](../action/action.md)
* [definição de espera personalizada](../building-journeys/wait-activity.md#custom)
* [definição de fuso horário](../building-journeys/timezone-management.md)

Essa configuração não é necessária se suas jornadas só usarem os dados locais provenientes de uma carga útil do evento. Por exemplo, se sua jornada for composta por um evento seguido por uma atividade de email que usa somente os dados do evento, não será necessário configurar uma fonte de dados.

Há dois tipos de fontes de dados:

* A fonte de dados pré-configurada da Adobe Experience Platform que define a conexão com o Serviço de perfil do cliente em tempo real. Essa fonte de dados é integrada. Consulte [esta página](../datasource/adobe-experience-platform-data-source.md).
* As fontes de dados externas que permitem definir uma conexão com sistemas externos. Essas são as que você pode criar. Consulte [esta página](../datasource/external-data-sources.md).

Para cada fonte de dados, você define as informações que serão recuperadas usando grupos de campos. Grupos de campos são conjuntos de campos que podem ser recuperados de uma fonte de dados. Consulte [esta página](../datasource/field-groups.md).

Para obter mais informações sobre como configurar uma fonte de dados da Adobe Experience Platform e uma fonte de dados externa, e como localizar e usar dados em uma jornada, assista a este [vídeo tutorial](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Estas são as etapas principais de configuração da fonte de dados:

>[!NOTE]
>
>A configuração da fonte de dados é sempre executada por um **usuário técnico**.

1. No menu superior, clique na guia **[!UICONTROL Data Sources]**.

   A lista das fontes de dados é exibida. Consulte [esta página](../about/user-interface.md) para obter mais informações sobre a interface.

   ![](../assets/journey18.png)

1. Em seguida, é possível adicionar grupos de campos à fonte de dados integrada (consulte [esta página](../datasource/adobe-experience-platform-data-source.md)) ou criar uma nova fonte de dados externa (consulte [esta página](../datasource/external-data-sources.md)) e grupos de campos associados (consulte [esta página](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clique em **[!UICONTROL Save]**.

   A fonte de dados agora está configurada e pronta para ser usada em suas jornadas.
