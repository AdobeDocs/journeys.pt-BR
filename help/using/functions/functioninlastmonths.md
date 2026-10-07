---
product: adobe campaign
title: inLastMonths
description: Saiba mais sobre a função inLastMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
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
source-wordcount: '44'
ht-degree: 20%
---
# inLastMonths {#inLastMonths}

Retorna verdadeiro se uma determinada data ou dateTime estiver entre agora e agora - meses delta.

## Categoria

Data

## Sintaxe da função

`inLastMonths(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inLastMonths(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna verdadeiro.
