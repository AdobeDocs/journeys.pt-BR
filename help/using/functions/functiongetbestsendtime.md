---
title: getBestSendTime
description: Saiba mais sobre a função getBestSendTime
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
source-wordcount: '239'
ht-degree: 3%

---


# getBestSendTime {#getBestSendTime}

Fornece um tempo preditivo do melhor tempo para enviar um email para um indivíduo.

Essa função usa uma pontuação calculada no Adobe Experience Platform. A pontuação calcula a propensão de clicar ou abrir um email no futuro com base no comportamento anterior. Observe que o algoritmo que calcula a pontuação precisa de uma certa quantidade de dados para funcionar. Como resultado, quando não tiver dados suficientes, o tempo padrão será aplicado. For more information, see [](../building-journeys/wait-activity.md).

Para usar essa função, é necessária uma [namespace](../event/selecting-the-namespace.md) .

>[!NOTE]
>
>Observe que a melhor pontuação de tempo de envio pode estar indisponível se não houver dados suficientes para executar o cálculo. Nesse caso, você será informado, no momento da publicação, de que o horário padrão se aplica.

## Categoria

Adobe Experience Platform

## Sintaxe da função

`getBestSendTime(<parameters>)`

## Parâmetros

| Parâmetro | Descrição | Tipo |
|--- |--- |--- |
| quantidade de tempo | Número de horas a considerar a partir do horário atual (máx.: 168) para otimizar o envio de email | `<integer>` |
| tipo de otimização | &quot;open&quot; ou &quot;click&quot; | `<string>` |
| tempo padrão em horas de espera | Caso as pontuações de tempo de envio previsíveis não estejam disponíveis | `<integer>` |

## Assinatura e tipo retornado

`getBestSendTime(<integer>,<string>,<integer>)`

Retorna dateTime.

## Exemplo

getBestSendTime(12,&quot;open&quot;,8)

Explicação :

A função retornará o melhor tempo para enviar uma mensagem nas próximas 12 horas, a fim de otimizar a probabilidade do indivíduo na instância da jornada para abri-la. Se não houver dados suficientes para executar o cálculo, o tempo retornado será em 8 horas a partir do horário atual.
