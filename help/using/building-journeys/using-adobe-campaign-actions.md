---
title: Usar ações do Adobe Campaign
description: Saiba mais sobre ações de Adobe Campaign
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
source-wordcount: '888'
ht-degree: 3%

---


# Usar ações do Adobe Campaign {#using_campaign_action}

Se você tiver Adobe Campaign Standard, as seguintes atividades de ação prontas para uso estão disponíveis: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>Para isso, é necessário configurar a ação integrada. Consulte [](../action/working-with-adobe-campaign.md).

Para cada um desses canais, selecione um **modelo** de mensagens transacionais do Adobe Campaign Standard. Na verdade, não [!DNL Journey Orchestration] é uma solução de envio de mensagens. Para os canais incorporados de email, SMS e push, confiamos nas Mensagens transacionais para executar o envio de mensagens. Isso significa que, se você quiser usar um determinado modelo de mensagem em suas viagens, deverá publicá-lo no Adobe Campaign Standard. Consulte esta [página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) para saber como usar este recurso.

>[!NOTE]
>
>O mensagen transacional Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for publicada, ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas seu evento associado não for, ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

![](../assets/journey59.png)

Você pode usar um evento (também conhecido como em tempo real) ou modelo de mensagens transacionais de perfil.

>[!NOTE]
>
>Quando enviamos mensagens transacionais em tempo real (rtEvent) ou quando roteamos mensagens com um sistema de terceiros graças a uma ação personalizada, uma configuração específica é necessária para o gerenciamento de fadiga, lista de bloqueios ou unsubscription. Por exemplo, se um atributo &quot;unsubscribe&quot; for armazenado no Adobe Experience Platform ou em um sistema de terceiros, uma condição terá de ser adicionada antes do envio da mensagem para verificar essa condição.

Quando você seleciona um modelo, todos os campos esperados na carga da mensagem são exibidos no painel de configuração da atividade em **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**. É necessário mapear cada um desses campos com o campo que deseja usar, a partir do evento ou da fonte de dados. Você também pode usar o editor de expressão avançado para passar um valor manualmente, executar a manipulação de dados em informações recuperadas (por exemplo, converter uma sequência em maiúsculas) ou usar funções como &quot;if, then, else&quot;. Consulte [](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## Email e SMS {#section_asc_51g_nhb}

Para **[!UICONTROL Email]** e **[!UICONTROL SMS]**, os parâmetros são idênticos.

>[!NOTE]
>
>Para email, se você estiver usando um modelo transacional de perfis, o mecanismo de unsubscription é manipulado prontamente por Campaign Standard. Basta adicionar um bloco **[!UICONTROL Unsubscription link]** de conteúdo ao modelo ([saiba mais](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Se você estiver usando um modelo baseado em eventos (rtEvent), precisará adicionar, na mensagem, um link que passe o email da pessoa no parâmetro URL e aponte para uma landing page de unsubscription. É necessário criar essa landing page e garantir que a decisão da pessoa de cancelar a inscrição seja transmitida à Adobe.

Primeiro, você precisa escolher um modelo de mensagem transacional. Consulte [](../building-journeys/about-action-activities.md).

Duas categorias estão disponíveis: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

Você pode definir facilmente onde recuperar o **[!UICONTROL Address]** ou o **[!UICONTROL Personalization Data]** usando a interface. É possível navegar pelos eventos e campos da fonte de dados disponíveis. Você também pode usar o editor de expressões avançado para casos de uso mais avançados, como o uso de uma fonte de dados que exija a passagem de parâmetros ou a realização de manipulações. Consulte [](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Essa categoria só estará visível se você selecionar um mensagen transacional &quot;evento&quot;. Para mensagens de &quot;perfil&quot;, o **[!UICONTROL Address]** campo é recuperado automaticamente do Adobe Campaign Standard pelo sistema.

Esses são os campos que o sistema exige para saber onde enviar a mensagem. Para um modelo de email, é o endereço de email. Para um SMS, é o número do telefone celular.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Não é possível passar uma coleção em dados de personalização. Se o email transacional ou o SMS espera coleções, ele não funcionará. Observe também que os dados de personalização têm um formato esperado (por exemplo: string, decimal etc.). Você deve ter cuidado para respeitar esses formatos esperados.

Esses são os campos esperados pela mensagem de Adobe Campaign Standard. Esses campos podem ser usados para personalizar a mensagem, aplicar formatação condicional ou selecionar uma variante de mensagem específica.

![](../assets/journey62.png)

## Empurrar {#section_im3_hvf_nhb}

Antes de usar a atividade de push, seu aplicativo móvel precisa ser configurado junto com o Campaign Standard para enviar notificações por push. Use este [artigo](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) para executar as etapas de implementação necessárias para dispositivos móveis.

Primeiro, você precisa escolher um aplicativo móvel na lista suspensa e um mensagen transacional. Consulte [](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Duas categorias estão disponíveis: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Essa categoria só estará visível se você selecionar uma mensagem de evento. Para mensagens de perfil, os **[!UICONTROL Target]** campos são recuperados automaticamente pelo sistema usando a reconciliação executada pelo Adobe Campaign Standard.

Nesta seção, é necessário definir o **[!UICONTROL Push platform]**. A lista suspensa permite selecionar **[!UICONTROL Apple Push Notification Server]** (iOS) ou **[!UICONTROL Firebase Cloud Messaging]** (Android). Como alternativa, você pode selecionar um campo específico de um evento ou de uma fonte de dados, ou definir uma expressão avançada.

Você também precisa definir o **[!UICONTROL Registration Token]**. A expressão depende de como o token é definido na carga do evento ou em outras [!DNL Journey Orchestration] informações. Pode ser um campo simples ou uma expressão mais complexa caso o token seja definido em uma coleção, por exemplo:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Não é possível passar uma coleção em dados de personalização. Se o push transacional espera coleções, ele não funcionará. Observe também que os dados de personalização têm um formato esperado (por exemplo: string, decimal etc.). Você deve ter cuidado para respeitar esses formatos esperados.

Esses são os campos esperados pelo modelo transacional usado na mensagem de Adobe Campaign Standard. Esses campos podem ser usados para personalizar a mensagem, aplicar formatação condicional ou selecionar uma variante de mensagem específica.
