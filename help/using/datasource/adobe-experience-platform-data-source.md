---
title: 'Fonte de dados do Adobe Experience Platform '
description: 'Saiba como configurar a fonte de dados da plataforma Adobe Experience '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Fonte de dados do Adobe Experience Platform {#concept_zrb_nqt_52b}

A fonte de dados da plataforma Experience define a conexão ao Serviço de perfil do cliente em tempo real. Essa fonte de dados é incorporada e pré-configurada. Não pode ser eliminada. Essa fonte de dados foi projetada para recuperar e usar dados do Serviço de Perfil do Cliente em Tempo Real (por exemplo, verifique se a pessoa que entrou em uma jornada é uma mulher). Ele permite que você use dados de perfil e dados de eventos de experiência. Para obter mais informações sobre o Serviço de perfil do cliente em tempo real, consulte esta [página](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

>[!NOTE]
>
>Você pode recuperar os 1000 eventos de experiência mais recentes criados há menos de um ano.

Para permitir a conexão com o Serviço de perfil do cliente em tempo real, precisamos usar uma chave para identificar uma pessoa e um namespace que contextualize a chave. Como resultado, você só poderá usar essa fonte de dados se suas viagens começarem com um evento que contenha uma chave e um namespace. Consulte [](../building-journeys/journey.md).

Você pode editar o grupo de campos pré-configurado chamado &quot;ProfileFieldGroup&quot;, adicionar novos e remover os que não são usados em nenhuma jornada de rascunho ou ao vivo. Consulte [](../datasource/field-groups.md).

Estas são as etapas principais para adicionar grupos de campos à fonte de dados integrada.

1. Na lista de fontes de dados, selecione a fonte de dados integrada da Plataforma de experiência.

   Isso abre o painel de configuração da fonte de dados no lado direito da tela.

   ![](../assets/journey23.png)

1. Clique em **[!UICONTROL Add a New Field Group]**para definir uma nova série de campos a serem recuperados. Consulte[](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selecione um esquema no **[!UICONTROL Schema]**menu suspenso. Este campo lista os esquemas Perfil e Eventos de experiência disponíveis na Plataforma. A criação do esquema não é realizada na Journey Orchestration. É executado na Plataforma de dados.
1. Selecione os campos que deseja usar.
1. Defina a duração do cache.
1. Clique em **[!UICONTROL Save]**.

Quando você coloca o cursor no nome de um grupo de campos, você verá dois ícones à direita. Eles permitem que você exclua e duplique o grupo de campos. Observe que o **[!UICONTROL Delete]**ícone só estará disponível se o grupo de campos não for usado em nenhuma jornada ao vivo ou de rascunho (informações exibidas no**[!UICONTROL Used in]** campo).
