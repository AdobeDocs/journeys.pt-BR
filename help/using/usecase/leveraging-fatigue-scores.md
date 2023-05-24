---
product: adobe campaign
title: Aproveitar pontuações de fadiga
description: Saiba como aproveitar as pontuações de fadiga no jornada
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 12%

---


# Aproveitamento da AI da jornada {#concept_dsh_1ry_wfb}

Esse caso de uso mostrará como aproveitar as pontuações de fadiga para evitar o excesso de solicitações de seus clientes em suas jornadas.

>[!NOTE]
>
>O recurso de pontuação preditiva de fadiga está disponível somente para clientes que usam o [Conector de dados do Adobe Experience Platform](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Configuração do evento {#section_ptb_ws1_ffb}

Siga as etapas descritas em [esta página](../event/about-events.md).

## Configuração da fonte de dados {#section_o3n_4yy_wfb}

Execute as seguintes etapas para selecionar os campos de pontuação de fadiga na fonte de dados integrada:

1. No painel de menus, selecione **[!UICONTROL Admin]**. Na seção **[!UICONTROL Data sources]**, clique em **[!UICONTROL Manage]**.
1. Selecione a fonte de dados integrada do Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Verifique se os campos necessários para o caso de uso foram selecionados.
1. Clique em **[!UICONTROL Add a New Field Group]**, selecione o **[!UICONTROL Profiles]** e adicione o **[!UICONTROL fatigueLevel]** e **[!UICONTROL fatigueScore]** campos (em _journeyAI > emailScore > fadiga_).

   ![](../assets/journeyuc3_1.png)

1. Clique em **[!UICONTROL Save]**.

## Construção da jornada {#section_uzm_pyy_wfb}

Para criar, validar e publicar a jornada, siga as etapas descritas em [esta página](../building-journeys/journey.md).

No nosso caso de uso, estamos aproveitando o **[!UICONTROL fatigueLevel]** campo. Você também pode usar a variável **[!UICONTROL fatigueScore]** campo.

Execute as seguintes etapas para aproveitar o nível de fadiga na jornada:

1. Adicione um evento e uma condição na jornada.

   ![](../assets/journeyuc2_14.png)

1. Escolha o tipo **[!UICONTROL Data Source Condition]** e clique no campo **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Usando o editor de expressões simples, procure pelo **[!UICONTROL fatigueLevel]** campo (_ExperiencePlatformDataSource > JourneyAIScores > Perfil > journeyAI > emailScore > fadiga_), solte-o à direita e crie a seguinte condição: &quot;fatigueLevel is equal to &quot;Low&quot;. Clique em **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   A expressão avançada é:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Na condição, crie dois outros caminhos para níveis de fadiga médios e altos.

   ![](../assets/journeyuc3_4.png)

1. Agora é possível adicionar ações diferentes para cada nível de fadiga.

   ![](../assets/journeyuc3_5.png)
