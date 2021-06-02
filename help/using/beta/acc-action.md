---
product: adobe campaign
title: Sobre a integração do Campaign Classic
description: Saiba mais sobre a integração do Campaign Classic
hide: true
hidefromtoc: true
feature: Jornadas
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 6%

---

# Integração com o Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Essa integração permite enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign Classic.

A conexão entre as instâncias Journey Orchestration e Campaign Classic é configurada pelo Adobe no momento do provisionamento.

>[!CAUTION]
>
> Essa integração é lançada como um beta privado. Não está disponível para todos os clientes do Journey Orchestration.

## Observações importantes

* Não há limitação de mensagens. Limitamos o número de mensagens que podem ser enviadas para 50.000/hora com base no nosso SLA Campaign Classic atual. Por isso, a orquestração de Jornadas deve ser usada somente em casos de uso unitários (eventos individuais, não segmentos).

* É necessário configurar uma ação na tela por modelo que deseja usar.

* Recomendamos usar uma instância dedicada do Centro de Mensagens que esteja hospedada para essa integração, a fim de evitar o impacto de outras operações do Campaign Classic que você possa ter realizado. O servidor de marketing pode ser hospedado ou no local. A build necessária é 21.1 Release Candidate.

* Não há validação de que a carga ou a mensagem de Campaign Classic esteja correta.

* Não é possível usar uma Campaign Classic action com uma qualificação de segmento.

## Pré-requisitos

No Campaign Classic, é necessário criar e publicar uma mensagem transacional e seu evento associado. Consulte a [documentação do Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

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

No Journey Orchestration, é necessário configurar uma ação por mensagem transacional. Siga estas etapas:

1. Crie uma nova ação. Consulte esta [seção](../action/action.md).
1. Insira um nome e uma descrição.
1. No campo **Action type**, selecione **Adobe Campaign Classic**.
1. Clique no campo **Payload** e cole um exemplo da carga JSON correspondente à mensagem Campaign Classic. Entre em contato com o Adobe para obter essa carga.
1. Ajuste os diferentes campos. Determinados campos, como parâmetros de canal e campos de personalização (ctx) precisam ser definidos como variáveis.
1. Clique em **Save**.

![](../assets/accintegration1.png)

Para cada ação configurada, uma atividade de ação está disponível na paleta Designer de jornadas.

## Adicionar uma mensagem em uma jornada

1. Projete a jornada, começando por um evento. Consulte esta [seção](../building-journeys/journey.md).
1. Na seção **Action** da paleta, selecione uma ação Campaign Classic e adicione-a à jornada.
1. Nos **Action parameters**, todos os campos esperados na carga da mensagem são exibidos. Você precisa mapear cada um desses campos com o campo que deseja usar, do evento ou da fonte de dados. Isso é semelhante às ações personalizadas. Consulte esta [seção](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
