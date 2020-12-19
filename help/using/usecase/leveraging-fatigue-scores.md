---
product: adobe campaign
solution: Journey Orchestration
title: Aproveitar pontuações de fadiga
description: Saiba como aproveitar as pontuações de fadiga em viagens
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Aproveitamento da AI da jornada {#concept_dsh_1ry_wfb}

Este caso de uso mostrará como aproveitar as pontuações de fadiga para evitar a solicitação excessiva de seus clientes em suas viagens.

>[!NOTE]
>
>O recurso de pontuação de fadiga preditiva só está disponível para clientes que usam o [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

## Configurar o evento {#section_ptb_ws1_ffb}

Siga as etapas descritas em [this page](../event/about-events.md).

## Configurar a fonte de dados {#section_o3n_4yy_wfb}

Execute as seguintes etapas para selecionar os campos de pontuação de fadiga na fonte de dados incorporada:

1. No menu superior, clique na guia **[!UICONTROL Data Sources]** e selecione a fonte de dados Adobe Experience Platform integrada.

   ![](../assets/journey23.png)

1. Verifique se os campos necessários para o caso de uso estão selecionados.
1. Clique em **[!UICONTROL Add a New Field Group]**, selecione o modelo **[!UICONTROL Profiles]** e adicione os campos **[!UICONTROL fatigueLevel]** e **[!UICONTROL fatigueScore]** (em _jornadaAI > emailScore > fadiga_).

   ![](../assets/journeyuc3_1.png)

1. Clique em **[!UICONTROL Save]**.

## Construir a jornada {#section_uzm_pyy_wfb}

Para criar, validar e publicar a jornada, siga as etapas descritas em [esta página](../building-journeys/journey.md).

Em nosso caso de uso, estamos aproveitando o campo **[!UICONTROL fatigueLevel]**. Você também pode usar o campo **[!UICONTROL fatigueScore]**.

Execute as seguintes etapas para alavancar o nível de fadiga em sua jornada:

1. Adicione um evento e uma condição em sua jornada.

   ![](../assets/journeyuc2_14.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e clique no campo **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Usando o editor de expressões simples, procure o campo **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Perfil > jornadaAI > emailScore > fadiga_), solte-o para a direita e crie a seguinte condição: &quot;fadigaLevel é igual a &quot;Baixo&quot;. Clique em **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   A expressão avançada é:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Na condição, crie outros dois caminhos para níveis de fadiga médios e altos.

   ![](../assets/journeyuc3_4.png)

1. Agora é possível adicionar diferentes ações para cada nível de fadiga.

   ![](../assets/journeyuc3_5.png)
