---
product: adobe campaign
title: Configuração da fonte de dados
description: Saiba como configurar a fonte de dados para o caso de uso simples do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 31%
---
# Configuração da fonte de dados{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


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
