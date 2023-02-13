---
product: adobe campaign
title: inLastMonths
description: Saiba mais sobre a função emLastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora - meses delta.

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

Retorna um booleano.

## Exemplos

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna true.
