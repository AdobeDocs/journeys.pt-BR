---
product: adobe campaign
title: Trabalhar com o Adobe Campaign
description: Saiba mais sobre as ações do Adobe Campaign
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 4%

---

# Trabalhar com o Adobe Campaign {#using_adobe_campaign}

## Uso do Adobe Campaign Standard {#using_adobe_campaign_standard}

Você pode enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais da Adobe Campaign Standard.

[!DNL Journey Orchestration] O vem com uma ação pronta para uso que permite a conexão com o Adobe Campaign Standard.

A mensagem transacional do Campaign Standard e seu evento associado devem ser publicados para serem usados no Journey Orchestration. Se o evento for publicado, mas a mensagem não for , ele não estará visível na interface do Journey Orchestration. Se a mensagem for publicada, mas o evento associado não for , ela estará visível na interface do Journey Orchestration, mas não poderá ser usada.

>[!NOTE]
>
>Uma regra de limitação de 13 chamadas por segundo é definida automaticamente para ações do Adobe Campaign Standard assim que a integração do Adobe Campaign Standard é configurada. Isso corresponde à escala oficial do Adobe Campaign Standard Transactional Messaging.
>
>Leia mais sobre SLAs de mensagens transacionais em [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Estas são as etapas para configurá-lo:

1. Na lista **[!UICONTROL Actions]**, clique na ação **[!UICONTROL AdobeCampaignStandard]** incorporada. O painel de configuração de ação é aberto no lado direito da tela.

   ![](../assets/actioncampaign.png)

1. Copie o URL da instância do Adobe Campaign Standard e cole-o no campo **[!UICONTROL URL]** .

1. Clique em **[!UICONTROL Test the instance URL]** para testar a validade da instância.

   >[!NOTE]
   >
   >Este teste verifica se:
   >
   >O host é &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; ou &quot;.adls.adobe.com&quot;.
   >
   >O URL começa com https,
   >
   >O ORG associado a esta instância do Adobe Campaign Standard é o mesmo que o Journey Orchestration ORG.

Ao projetar a jornada, três ações estarão disponíveis na categoria **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulte [Uso de ações do Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Os** eventos de Reações também permitirão reagir a cliques em mensagens, aberturas, etc. (consulte [Eventos de reação](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se estiver usando um sistema de terceiros para enviar mensagens, será necessário adicionar e configurar uma ação personalizada. Consulte [Sobre a configuração de ação personalizada](../action/about-custom-action-configuration.md).

## Uso do Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

Essa integração está disponível para o Adobe Campaign Classic v7 a partir da versão 21.1 e Adobe Campaign v8. Ele permite enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign.

A conexão entre as instâncias do Journey Orchestration e do Campaign é configurada pelo Adobe no momento do provisionamento.

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-v7-v8-use-case.md).

Para cada ação configurada, uma atividade de ação está disponível na paleta Designer de jornadas. Consulte esta [seção](../building-journeys/using-adobe-campaign-actions.md).

### Observações importantes

* Não há limitação de mensagens. Limitamos o número de mensagens que podem ser enviadas para 50.000/hora com base em nosso SLA atual do Campaign. Por isso, a orquestração de Jornadas deve ser usada somente em casos de uso unitários (eventos individuais, não segmentos).

* É necessário configurar uma ação na tela por modelo que deseja usar. Você precisa configurar uma ação no Journey Orchestration para cada template que deseja usar do Adobe Campaign.

* Recomendamos que você use uma instância dedicada do Centro de Mensagens que esteja hospedada para essa integração, a fim de evitar o impacto de outras operações do Campaign que possam ter sido realizadas. O servidor de marketing pode ser hospedado ou no local. A build necessária é 21.1 Release Candidate ou superior.

* Não há validação de que a carga ou a mensagem do Campaign esteja correta.

* Não é possível usar uma ação Campanha com um evento de qualificação de segmento.

### Pré-requisitos

No Campaign, é necessário criar e publicar uma mensagem transacional e seu evento associado. Consulte a [documentação do Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Você pode criar sua carga JSON correspondente a cada mensagem seguindo o padrão abaixo. Em seguida, você colará essa carga ao configurar a ação no Journey Orchestration (veja abaixo)

Aqui está um exemplo:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **canal**: o canal definido para o template transacional do Campaign
* **eventType**: o nome interno do evento do Campaign
* **ctx**: com base na personalização que você tem em sua mensagem.

### Configurar a ação

No Journey Orchestration, é necessário configurar uma ação por mensagem transacional. Siga estas etapas:

1. Crie uma nova ação. Consulte esta [seção](../action/action.md).
1. Insira um nome e uma descrição.
1. No campo **Action type**, selecione **Adobe Campaign Classic**.
1. Clique no campo **Payload** e cole um exemplo da carga JSON correspondente à mensagem do Campaign. Entre em contato com o Adobe para obter essa carga.
1. Ajuste os diferentes campos para serem estáticos ou variáveis, dependendo de se deseja mapeá-los na tela de Jornada. Determinados campos, como parâmetros de canal para endereços de email e campos de personalização (ctx), você provavelmente desejará defini-los como variáveis para mapeamento no contexto da jornada.
1. Clique em **Save**.

![](../assets/accintegration1.png)


