---
title: Uso de um segmento
description: Saiba como usar um segmento
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
source-git-commit: b238c1851ae640b3146b8457931e1c416387c76a
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---



# Uso de segmentos em condições {#using-a-segment}

>A guia de segmentos e a criação/modificação de segmentos no Journey Orchestration estarão disponíveis em 15 de junho.

Esta seção explica como usar um segmento em uma condição de jornada.
Para saber como usar um evento de qualificação **de** segmento em sua jornada, consulte atividades [de](../building-journeys/event-activities.md#segment-qualification)Eventos.

Para usar um segmento em uma condição de jornada, siga estas etapas:

1. Abra uma jornada, solte uma atividade de **Condição** e escolha a Condição **da Fonte**de Dados.
   ![](../assets/journey47.png)
1. Clique em **Adicionar um caminho** para cada caminho extra necessário. Para cada caminho, clique no campo **Expressão** .
   ![](../assets/segment3.png)
1. No lado esquerdo, desdobre o nó **Segmentos** . Arraste e solte o segmento que deseja usar para sua condição. Por padrão, a condição no segmento é verdadeira.
   ![](../assets/segment4.png)

Para obter mais informações sobre as condições de viagem e como usar o editor de expressão simples, consulte as atividades de [condição](../building-journeys/condition-activity.md#about_condition).
