---
product: adobe campaign
solution: Journey Orchestration
title: Usar ações do Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 5%

---


# Usar ações do Adobe Campaign {#using_campaign_action}

Se você tiver o Adobe Campaign Standard, as seguintes atividades de ação prontas para uso estarão disponíveis: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>Para isso, é necessário configurar a ação incorporada. Consulte [esta página](../action/working-with-adobe-campaign.md).

Para cada um desses canais, selecione um **template** de Mensagens Transacionais do Adobe Campaign Standard. Na verdade, [!DNL Journey Orchestration] não é uma solução de envio de mensagens. Para os canais incorporados de email, SMS e push, dependemos de Mensagens transacionais para executar o envio de mensagens. Isso significa que, se você quiser usar um determinado template de mensagem em suas jornadas, deverá publicá-lo no Adobe Campaign Standard. Consulte [esta página](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) para saber como usar este recurso.

>[!NOTE]
>
>A mensagem transacional do Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for , ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas o evento associado não for , ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

![](../assets/journey59.png)

Você pode usar um evento (também conhecido como tempo real) ou um modelo de mensagens transacionais de perfil.

>[!NOTE]
>
>Quando enviamos mensagens transacionais em tempo real (rtEvent) ou roteamos mensagens com um sistema de terceiros graças a uma ação personalizada, uma configuração específica é necessária para o gerenciamento de fadiga, lista de bloqueios ou unsubscription. Por exemplo, se um atributo &quot;unsubscribe&quot; for armazenado no Adobe Experience Platform ou em um sistema de terceiros, uma condição terá de ser adicionada antes do envio da mensagem para verificar essa condição.

Ao selecionar um modelo, todos os campos esperados na carga da mensagem são exibidos no painel de configuração da atividade em **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**. Você precisa mapear cada um desses campos com o campo que deseja usar, do evento ou da fonte de dados. Você também pode usar o editor de expressão avançado para transmitir um valor manualmente, executar a manipulação de dados em informações recuperadas (por exemplo, converter uma sequência em maiúsculas) ou usar funções como &quot;if, then, else&quot;. Consulte [esta página](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## Email e SMS {#section_asc_51g_nhb}

Para **[!UICONTROL Email]** e **[!UICONTROL SMS]**, os parâmetros são idênticos.

>[!NOTE]
>
>Para emails, se estiver usando um template transacional de perfis, o mecanismo de unsubscription é manipulado pronto para uso pelo Campaign Standard. Basta adicionar um bloco de conteúdo **[!UICONTROL Unsubscription link]** no modelo ([saiba mais](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Se estiver usando um modelo baseado em eventos (rtEvent), será necessário adicionar, na mensagem, um link que passe o email da pessoa no parâmetro de URL e aponte para uma landing page de unsubscription. Você precisa criar essa landing page e garantir que a decisão da pessoa de cancelar a assinatura seja transmitida ao Adobe.

Primeiro, você precisa escolher um template de mensagem transacional. Consulte [esta página](../building-journeys/about-action-activities.md).

Duas categorias estão disponíveis: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

Você pode definir facilmente onde recuperar o **[!UICONTROL Address]** ou o **[!UICONTROL Personalization Data]** usando a interface. Você pode navegar pelos eventos e campos da fonte de dados disponíveis. Você também pode usar o editor de expressão avançado para casos de uso mais avançados, como o uso de uma fonte de dados que requer a passagem de parâmetros ou a execução de manipulações. Consulte [esta página](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Esta categoria só estará visível se você selecionar uma mensagem transacional de &quot;evento&quot;. Para mensagens de &quot;perfil&quot;, o campo **[!UICONTROL Address]** é automaticamente recuperado do Adobe Campaign Standard pelo sistema.

Esses são os campos que o sistema requer para saber onde enviar a mensagem. Para um modelo de email, é o endereço de email. Para um SMS, é o número do celular.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Não é possível passar uma coleção em dados de personalização. Se o email transacional ou SMS espera coleções, ele não funcionará. Observe também que os dados de personalização têm um formato esperado (por exemplo: string, decimal, etc.). Você deve ter cuidado para respeitar esses formatos esperados.

Esses são os campos esperados pela mensagem do Adobe Campaign Standard. Esses campos podem ser usados para personalizar a mensagem, aplicar formatação condicional ou selecionar uma variante de mensagem específica.

![](../assets/journey62.png)

## Empurrar {#section_im3_hvf_nhb}

Antes de usar a atividade de push, o aplicativo móvel precisa ser configurado junto com o Campaign Standard para enviar notificações por push. Use este [artigo](https://helpx.adobe.com/br/campaign/kb/integrate-mobile-sdk.html) para tomar as etapas de implementação necessárias para dispositivos móveis.

Primeiro, você precisa escolher um aplicativo móvel na lista suspensa e uma mensagem transacional. Consulte [esta página](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Duas categorias estão disponíveis: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Esta categoria só estará visível se você selecionar uma mensagem de evento. Para mensagens de perfil, os campos **[!UICONTROL Target]** são automaticamente recuperados pelo sistema usando a reconciliação executada pelo Adobe Campaign Standard.

Nesta seção, você precisa definir o **[!UICONTROL Push platform]**. A lista suspensa permite selecionar **[!UICONTROL Apple Push Notification Server]** (iOS) ou **[!UICONTROL Firebase Cloud Messaging]** (Android). Como alternativa, é possível selecionar um campo específico de um evento ou fonte de dados ou definir uma expressão avançada.

Você também precisa definir o **[!UICONTROL Registration Token]**. A expressão depende de como o token é definido na carga do evento ou em outras informações [!DNL Journey Orchestration]. Pode ser um campo simples ou uma expressão mais complexa caso o token seja definido em uma coleção, por exemplo:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Não é possível passar uma coleção em dados de personalização. Se o push transacional espera coleções, ele não funcionará. Observe também que os dados de personalização têm um formato esperado (por exemplo: string, decimal, etc.). Você deve ter cuidado para respeitar esses formatos esperados.

Esses são os campos esperados pelo template transacional usado em sua mensagem do Adobe Campaign Standard. Esses campos podem ser usados para personalizar a mensagem, aplicar formatação condicional ou selecionar uma variante de mensagem específica.
