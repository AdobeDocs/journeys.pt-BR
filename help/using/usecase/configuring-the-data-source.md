---
product: adobe campaign
solution: Journey Orchestration
title: Configurar a fonte de dados
description: Saiba como configurar a fonte de dados para o caso de uso simples do jornada
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%

---


# Configurar a fonte de dados{#concept_ax3_bcy_w2b}

Em nosso caso de uso, queremos usar dados de personalização para nossas mensagens. Também precisamos verificar se a pessoa é mulher. Essas informações são armazenadas no banco de dados do Perfil do cliente em tempo real. O **usuário técnico** precisa verificar se esses campos estão definidos na fonte de dados integrada do Adobe Experience Platform.

Para obter informações adicionais sobre a configuração da fonte de dados, consulte [esta página](../datasource/about-data-sources.md).

1. No menu superior, clique na guia **[!UICONTROL Data Sources]** e selecione a fonte de dados integrada do Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Nos grupos de campos, verifique se os seguintes campos estão selecionados:

   * _pessoa > nome > nome_
   * _pessoa > nome > sobrenome_
   * _pessoa > gênero_
   * _email pessoal > endereço_

1. Clique em **[!UICONTROL Save]**.

A fonte de dados agora está configurada e pronta para ser usada no jornada.
