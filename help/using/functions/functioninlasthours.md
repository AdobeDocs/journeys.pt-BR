---
product: adobe campaign
title: inLastHours
description: Saiba mais sobre a função em Últimas horas
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastHours {#inLastHours}

Retorna verdadeiro se a data e hora especificadas estiverem entre agora e agora - delta horas.

## Categoria

Data

## Sintaxe da função

`inLastHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inLastHours(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Retorna verdadeiro.

`inLastHours(@{MyEvent.timestamp}, 4)`

Retorna verdadeiro.
