---
product: adobe campaign
title: inLastHours
description: Saiba mais sobre a função emLastHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 17%

---

# inLastHours {#inLastHours}

Retorna verdadeiro se a hora da data especificada estiver entre agora e agora - horas delta.

## Categoria

Data 

## Sintaxe da função

`inLastHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inLastHours(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

Retorna true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Retorna true.
