---
title: Configurar a fonte de dados
description: Saiba como configurar a fonte de dados para o caso de uso simples da jornada
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 6%

---


# Configurar a fonte de dados{#concept_ax3_bcy_w2b}

Em nosso caso de uso, queremos usar dados de personalização para nossas mensagens. Também precisamos verificar se a pessoa é uma mulher. Essas informações são armazenadas no banco de dados do Perfil do cliente em tempo real. O usuário **** técnico precisa verificar se esses campos estão definidos na fonte de dados Adobe Experience Platform integrada.

Para obter informações adicionais sobre a configuração da fonte de dados, consulte [](../datasource/about-data-sources.md).

1. No menu superior, clique na **[!UICONTROL Data Sources]** guia e selecione a fonte de dados Adobe Experience Platform integrada.

   ![](../assets/journey23.png)

1. Nos grupos de campos, verifique se os seguintes campos estão selecionados:

   * _pessoa > nome > nome_
   * _pessoa > nome > sobrenome_
   * _pessoa > sexo_
   * _personalEmail > endereço_

1. Clique em **[!UICONTROL Save]**.

A fonte de dados agora está configurada e pronta para ser usada em sua jornada.
