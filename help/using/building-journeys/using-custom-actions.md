---
product: adobe campaign
title: Usar ações personalizadas
description: Saiba mais sobre atividades de ação
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---

# Usar ações personalizadas {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


O painel de configuração de atividade mostra os parâmetros de configuração de URL e os parâmetros de autenticação configurados para a ação personalizada. [Saiba mais](../action/about-custom-action-configuration.md).

## Configurar o URL

### Caminho dinâmico

Se a URL incluir um caminho dinâmico, especifique o caminho no campo **[!UICONTROL Path]**.

>[!NOTE]
>
>Não é possível definir a parte estática do URL na jornada, mas na configuração global da ação personalizada. [Saiba mais](../action/about-custom-action-configuration.md).

Para concatenar campos e cadeias de caracteres de texto sem formatação, use as funções String ou o sinal de adição (+) no editor de expressão avançado. Coloque cadeias de texto sem formatação entre aspas simples (&#39;) ou entre aspas duplas (&quot;). [Saiba mais](../expression/expressionadvanced.md).

Esta tabela mostra um exemplo de configuração:

| Campo | Valor |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Caminho | `The id of marketingCampaign + '/messages'` |

O URL concatenado tem este formato:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;ID da campanha\>`/messages`

![](../assets/journey-custom-action-url.png)

### Cabeçalhos

A seção **[!UICONTROL URL Configuration]** mostra os campos de cabeçalho dinâmico, mas não os campos de cabeçalho constantes. Os campos de cabeçalho dinâmico são campos de cabeçalho HTTP cujo valor é configurado como uma variável. [Saiba mais](../action/about-custom-action-configuration.md).

Se necessário, especifique o valor dos campos de cabeçalho dinâmico:

1. Selecione a ação personalizada na jornada.
1. No painel de configuração, clique no ícone de lápis ao lado do campo de cabeçalho na seção **[!UICONTROL URL Configuration]**.

   ![](../assets/journey-dynamicheaderfield.png)

1. Selecione um campo e clique em **[!UICONTROL OK]**.

## Parâmetros de ação

Na seção **[!UICONTROL Action parameters]**, você verá os parâmetros de mensagem definidos como _&quot;Variável&quot;_. Para esses parâmetros, você pode definir onde obter essas informações (por exemplo: eventos, fontes de dados), transmitir valores manualmente ou usar o editor de expressão avançado para casos de uso avançados. Casos de uso avançados podem ser manipulação de dados e outro uso de função. [Saiba mais](../expression/expressionadvanced.md).

**Tópicos relacionados**

[Configurar uma ação](../action/about-custom-action-configuration.md)
