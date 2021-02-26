---
product: adobe campaign
solution: Journey Orchestration
title: Sobre a integração com o Campaign Classic
description: Saiba mais sobre a integração com o Campaign Classic
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 937b7235d41fe7f0395e303736974e32eea8558f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Integração com o Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Essa integração permite enviar emails, notificações por push e SMS usando os recursos de Mensagens Transacionais da Adobe Campaign Classic.

A conexão entre as instâncias Journey Orchestration e Campaign Classic é configurada por Adobe no momento do provisionamento.

>[!CAUTION]
>
> Essa integração é lançada como um beta privado. Não está disponível para todos os clientes do Journey Orchestration.

## Observações importantes

* Não há limitação de mensagens. Limitamos o número de mensagens que podem ser enviadas para 50.000/hora com base no nosso atual SLA de Campaign Classic. Por esta razão, a orquestração da Jornada só deve ser utilizada em casos de utilização unitária (eventos individuais, não segmentos).

* É necessário configurar uma ação na tela de desenho por modelo que deseja usar.

* Recomendamos que você use uma instância dedicada do Centro de mensagens hospedada para essa integração, a fim de evitar o impacto de outras operações de Campaign Classic que você possa ter em andamento. O servidor de marketing pode ser hospedado ou no local. A compilação necessária é o candidato à versão 21.1.

* Não há validação de que a carga ou a mensagem Campaign Classic esteja correta.

* Não é possível usar uma Campaign Classic com uma qualificação de segmento.

## Pré-requisitos

No Campaign Classic, é necessário criar e publicar um mensagen transacional e seu evento associado. Consulte a [documentação da Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Entre em contato com o Adobe para obter a carga JSON correspondente a cada mensagem. Em seguida, você colará essa carga ao configurar a ação no Journey Orchestration (veja abaixo).

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

## Configurar a ação

No Journey Orchestration, é necessário configurar uma ação por mensagen transacional. Siga estas etapas:

1. Crie uma nova ação. Consulte esta [seção](../action/action.md).
1. Insira um nome e uma descrição.
1. No campo **Tipo de ação**, selecione **Adobe Campaign Classic**.
1. Clique no campo **Payload** e cole um exemplo da carga JSON correspondente à mensagem Campaign Classic. Entre em contato com a Adobe para obter esta carga.
1. Ajuste os diferentes campos. Determinados campos, como parâmetros de canal e campos de personalização (ctx), precisam ser definidos como variáveis.
1. Clique em **Save**.

![](../assets/accintegration1.png)

Para cada ação configurada, uma atividade de ação está disponível na paleta Designer de jornadas.

## Adicionar uma mensagem em uma jornada

1. Projete sua jornada, começando com um evento. Consulte esta [seção](../building-journeys/journey.md).
1. Na seção **Action** da paleta, selecione uma ação de Campaign Classic e adicione-a à sua jornada.
1. Em **Parâmetros de ação**, todos os campos esperados na carga da mensagem são exibidos. É necessário mapear cada um desses campos com o campo que deseja usar, a partir do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

