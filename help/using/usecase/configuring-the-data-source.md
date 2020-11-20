---
product: adobe campaign
solution: Journey Orchestration
title: Configurar a fonte de dados
description: Saiba como configurar a fonte de dados para o caso de uso simples da jornada
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 6%

---


# Configurar a fonte de dados{#concept_ax3_bcy_w2b}

Em nosso caso de uso, queremos usar dados de personalização para nossas mensagens. Também precisamos verificar se a pessoa é uma mulher. Essas informações são armazenadas no banco de dados do Perfil do cliente em tempo real. O usuário **** técnico precisa verificar se esses campos estão definidos na fonte de dados Adobe Experience Platform integrada.

Para obter informações adicionais sobre a configuração da fonte de dados, consulte [esta página](../datasource/about-data-sources.md).

1. No menu superior, clique na **[!UICONTROL Data Sources]** guia e selecione a fonte de dados Adobe Experience Platform integrada.

   ![](../assets/journey23.png)

1. Nos grupos de campos, verifique se os seguintes campos estão selecionados:

   * _pessoa > nome > nome_
   * _pessoa > nome > sobrenome_
   * _pessoa > sexo_
   * _personalEmail > endereço_

1. Clique em **[!UICONTROL Save]**.

A fonte de dados agora está configurada e pronta para ser usada em sua jornada.
