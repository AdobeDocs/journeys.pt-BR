---
product: adobe campaign
solution: Journey Orchestration
title: Usar um segmento
description: Saiba como usar um segmento
feature: Jornada
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# Uso de segmentos em condições {#using-a-segment}

Esta seção explica como usar um segmento em uma condição de jornada. Para saber como usar um evento **[!UICONTROL Segment qualification]** em sua jornada, consulte esta [seção](../building-journeys/segment-qualification-events.md).

Para usar um segmento em uma condição de jornada, siga estas etapas:

1. Abra uma jornada, solte uma atividade **[!UICONTROL Condition]** e escolha a **Condição da fonte de dados**.
   ![](../assets/journey47.png)

1. Clique em **[!UICONTROL Add a path]** para cada caminho extra necessário. Para cada caminho, clique no campo **[!UICONTROL Expression]** .

   ![](../assets/segment3.png)

1. No lado esquerdo, expanda o nó **[!UICONTROL Segments]** . Arraste e solte o segmento que deseja usar para sua condição. Por padrão, a condição no segmento é verdadeira.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Somente os indivíduos com os status de participação do segmento **Realizado** e **Existente** serão considerados membros do segmento. Para obter mais informações sobre como avaliar um segmento, consulte a [documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obter mais informações sobre as condições da jornada e como usar o editor de expressão simples, consulte [Condition activity](../building-journeys/condition-activity.md#about_condition).