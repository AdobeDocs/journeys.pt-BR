---
product: adobe campaign
title: Usar ações personalizadas
description: Saiba mais sobre atividades de ação
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# Usar ações personalizadas {#section_f2c_hbg_nhb}

O painel de configuração de atividade mostra os parâmetros de configuração de URL e os parâmetros de autenticação configurados para a ação personalizada. [Saiba mais](../action/about-custom-action-configuration.md).

## Configurar o URL

### Caminho dinâmico

Se o URL incluir um caminho dinâmico, especifique o caminho na variável **[!UICONTROL Path]** campo.

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

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Cabeçalhos

A variável **[!UICONTROL URL Configuration]** mostra os campos de cabeçalho dinâmico, mas não os campos de cabeçalho constantes. Os campos de cabeçalho dinâmico são campos de cabeçalho HTTP cujo valor é configurado como uma variável. [Saiba mais](../action/about-custom-action-configuration.md).

Se necessário, especifique o valor dos campos de cabeçalho dinâmico:

1. Selecione a ação personalizada na jornada.
1. No painel de configuração, clique no ícone de lápis ao lado do campo de cabeçalho no **[!UICONTROL URL Configuration]** seção.

   ![](../assets/journey-dynamicheaderfield.png)

1. Selecione um campo e clique em **[!UICONTROL OK]**.

## Parâmetros de ação

No **[!UICONTROL Action parameters]** você verá os parâmetros de mensagem definidos como _&quot;Variável&quot;_. Para esses parâmetros, você pode definir onde obter essas informações (por exemplo: eventos, fontes de dados), transmitir valores manualmente ou usar o editor de expressão avançado para casos de uso avançados. Casos de uso avançados podem ser manipulação de dados e outro uso de função. [Saiba mais](../expression/expressionadvanced.md).

**Tópicos relacionados**

[Configurar uma ação](../action/about-custom-action-configuration.md)
