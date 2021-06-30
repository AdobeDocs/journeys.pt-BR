---
product: adobe campaign
title: Aproveitar pontuações de fadiga
description: Saiba como aproveitar as pontuações de fadiga no jornada
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 10%

---


# Aproveitamento da AI da jornada {#concept_dsh_1ry_wfb}

Esse caso de uso mostrará como aproveitar as pontuações de fadiga para evitar o excesso de solicitações dos clientes em suas jornadas.

>[!NOTE]
>
>O recurso de pontuação de fadiga preditiva só está disponível para clientes que usam o [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Configuração do evento {#section_ptb_ws1_ffb}

Siga as etapas descritas em [this page](../event/about-events.md).

## Configuração da fonte de dados {#section_o3n_4yy_wfb}

Execute as seguintes etapas para selecionar os campos de pontuação de fadiga na fonte de dados incorporada:

1. No menu superior, clique na guia **[!UICONTROL Data Sources]** e selecione a fonte de dados integrada do Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Verifique se os campos necessários para o caso de uso estão selecionados.
1. Clique em **[!UICONTROL Add a New Field Group]**, selecione o modelo **[!UICONTROL Profiles]** e adicione os campos **[!UICONTROL fatigueLevel]** e **[!UICONTROL fatigueScore]** (em _journeyAI > emailScore > fadiga_).

   ![](../assets/journeyuc3_1.png)

1. Clique em **[!UICONTROL Save]**.

## Construção da jornada {#section_uzm_pyy_wfb}

Para criar, validar e publicar a jornada, siga as etapas descritas em [this page](../building-journeys/journey.md).

No nosso caso de uso, estamos aproveitando o campo **[!UICONTROL fatigueLevel]**. Também é possível usar o campo **[!UICONTROL fatigueScore]**.

Execute as seguintes etapas para aproveitar o nível de fadiga na jornada:

1. Adicione um evento e uma condição na jornada.

   ![](../assets/journeyuc2_14.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e clique no campo **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Usando o editor de expressão simples, procure o campo **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Profile > journeyAI > emailScore > fadiga_), solte-o à direita e crie a seguinte condição: &quot;fatigueLevel é igual a &quot;Baixo&quot;. Clique em **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   A expressão avançada é:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Na condição , crie dois outros caminhos para níveis de fadiga médio e alto.

   ![](../assets/journeyuc3_4.png)

1. Agora é possível adicionar diferentes ações para cada nível de fadiga.

   ![](../assets/journeyuc3_5.png)
