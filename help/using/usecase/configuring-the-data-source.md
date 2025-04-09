---
product: adobe campaign
title: Configuração da fonte de dados
description: Saiba como configurar a fonte de dados para o caso de uso simples do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 5%

---

# Configuração da fonte de dados{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


No nosso caso de uso, queremos usar dados de personalização para nossas mensagens. Também precisamos verificar se a pessoa é uma mulher. Essas informações são armazenadas no banco de dados do Perfil do cliente em tempo real. O **usuário técnico** precisa verificar se esses campos estão definidos na fonte de dados interna do Adobe Experience Platform.

Para obter informações adicionais sobre a configuração da fonte de dados, consulte [esta página](../datasource/about-data-sources.md).

1. No painel de menus, selecione **[!UICONTROL Admin]**. Na seção **[!UICONTROL Data sources]**, clique em **[!UICONTROL Manage]**.
1. Selecione a fonte de dados integrada do Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Nos grupos de campos, verifique se os seguintes campos estão selecionados:

   * _pessoa > nome > firstName_
   * _pessoa > nome > lastName_
   * _pessoa > gênero_
   * _personalEmail > endereço_

1. Clique em **[!UICONTROL Save]**.

A fonte de dados agora está configurada e pronta para ser usada no jornada.
