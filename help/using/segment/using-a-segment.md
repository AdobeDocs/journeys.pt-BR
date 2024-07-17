---
product: adobe campaign
title: Uso de segmentos em condições
description: Saiba como usar um segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 5%

---

# Uso de segmentos em condições {#using-a-segment}

Esta seção explica como usar um segmento em uma condição de jornada. Para saber como usar um evento **[!UICONTROL Segment qualification]** em sua jornada, consulte esta [seção](../building-journeys/segment-qualification-events.md).

Para usar um segmento em uma condição de jornada, siga estas etapas:

1. Abra uma jornada, solte uma atividade **[!UICONTROL Condition]** e escolha a **Condição Source de Dados**.
   ![](../assets/journey47.png)

1. Clique em **[!UICONTROL Add a path]** para cada caminho extra necessário. Para cada caminho, clique no campo **[!UICONTROL Expression]**.

   ![](../assets/segment3.png)

1. No lado esquerdo, expanda o nó **[!UICONTROL Segments]**. Arraste e solte o segmento que deseja usar para a sua condição. Por padrão, a condição no segmento é verdadeira.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Apenas indivíduos com os status de participação de segmento **Realizado** e **Existente** serão considerados membros do segmento. Para obter mais informações sobre como avaliar um segmento, consulte a [documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obter mais informações sobre as condições de jornada e como usar o editor de expressões simples, consulte [Atividade de condição](../building-journeys/condition-activity.md#about_condition).
