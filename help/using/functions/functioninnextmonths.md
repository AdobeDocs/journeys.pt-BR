---
product: adobe campaign
title: inNextMonths
description: Saiba mais sobre a função em NextMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inNextMonths {#inNextMonths}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora + meses delta.

## Categoria

Data 

## Sintaxe da função

`inNextMonths(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextMonths(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Retorna true.
