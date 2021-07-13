---
product: adobe campaign
title: Sobre a integração do Campaign v7/v8
description: Saiba mais sobre a integração do Campaign v7/v8
feature: Jornadas
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 9%

---

# Trabalhar com o Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Essa integração está disponível para o Adobe Campaign Classic v7 a partir da versão 21.1 e Adobe Campaign v8. Ele permite enviar emails, notificações por push e SMS usando os recursos de Mensagens transacionais do Adobe Campaign.

A conexão entre as instâncias do Journey Orchestration e do Campaign é configurada pela Adobe no momento do provisionamento.

Um caso de uso completo é apresentado nesta [seção](../usecase/campaign-classic-use-case.md).

Para cada ação configurada, uma atividade de ação está disponível na paleta Designer de jornadas. Consulte esta [seção](../building-journeys/using-adobe-campaign-classic.md).

## Observações importantes

* Não há limitação de mensagens. Limitamos o número de mensagens que podem ser enviadas para 50.000/hora com base em nosso SLA atual do Campaign. Por isso, a orquestração de Jornadas deve ser usada somente em casos de uso unitários (eventos individuais, não segmentos).

* É necessário configurar uma ação na tela por modelo que deseja usar. Você precisa configurar uma ação no Journey Orchestration para cada template que deseja usar do Adobe Campaign.

* Recomendamos que você use uma instância dedicada do Centro de Mensagens que esteja hospedada para essa integração, a fim de evitar o impacto de outras operações do Campaign que possam ter sido realizadas. O servidor de marketing pode ser hospedado ou no local. A build necessária é 21.1 Release Candidate ou superior.

* Não há validação de que a carga ou a mensagem do Campaign esteja correta.

* Não é possível usar uma ação Campanha com um evento de qualificação de segmento.

## Pré-requisitos

No Campaign, é necessário criar e publicar uma mensagem transacional e seu evento associado. Consulte a [documentação do Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Você pode criar sua carga JSON correspondente a cada mensagem seguindo o padrão abaixo. Em seguida, você colará essa carga ao configurar a ação no Journey Orchestration (veja abaixo)

Exemplo:

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

## Configurar a ação

No Journey Orchestration, é necessário configurar uma ação por mensagem transacional. Siga estas etapas:

1. Crie uma nova ação. Consulte esta [seção](../action/action.md).
1. Insira um nome e uma descrição.
1. No campo **Action type**, selecione **Adobe Campaign Classic**.
1. Clique no campo **Payload** e cole um exemplo da carga JSON correspondente à mensagem do Campaign. Entre em contato com o Adobe para obter essa carga.
1. Ajuste os diferentes campos para serem estáticos ou variáveis, dependendo de se deseja mapeá-los na tela de Jornada. Determinados campos, como parâmetros de canal para endereços de email e campos de personalização (ctx), você provavelmente desejará defini-los como variáveis para mapeamento no contexto da jornada.
1. Clique em **Salvar**.

![](../assets/accintegration1.png)


