---
product: adobe campaign
title: Usar um segmento
description: Saiba como usar um segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Uso de segmentos em condições {#using-a-segment}

Esta seção explica como usar um segmento em uma condição de jornada. Para saber como usar um **[!UICONTROL Segment qualification]** na jornada, consulte esta seção [seção](../building-journeys/segment-qualification-events.md).

Para usar um segmento em uma condição de jornada, siga estas etapas:

1. Abra uma jornada, solte uma **[!UICONTROL Condition]** e escolha a **Condição da fonte de dados**.
   ![](../assets/journey47.png)

1. Clique em **[!UICONTROL Add a path]** para cada caminho extra necessário. Para cada caminho, clique no botão **[!UICONTROL Expression]** campo.

   ![](../assets/segment3.png)

1. No lado esquerdo, expanda-se **[!UICONTROL Segments]** nó . Arraste e solte o segmento que deseja usar para sua condição. Por padrão, a condição no segmento é verdadeira.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Somente os indivíduos com a variável **Realizado** e **Existente** os status de participação do segmento serão considerados membros do segmento. Para obter mais informações sobre como avaliar um segmento, consulte [Documentação do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Para obter mais informações sobre as condições de jornada e como usar o editor de expressão simples, consulte [Atividade de condição](../building-journeys/condition-activity.md#about_condition).
