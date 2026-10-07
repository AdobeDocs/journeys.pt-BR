---
product: adobe campaign
title: inLastHours
description: Saiba mais sobre a função em Últimas horas
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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
