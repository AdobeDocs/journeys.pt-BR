---
product: adobe campaign
title: inLastDays
description: Saiba mais sobre a função emLastDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inLastDays {#inLastDays}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora - dias delta.

## Categoria

Data

## Sintaxe da função

`inLastDays(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inLastDays(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

Retorna true.
