---
product: adobe campaign
title: inNextDays
description: Saiba mais sobre a função em NextDays
feature: Journeys
role: Developer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

Retorna verdadeiro se uma determinada data ou dateTime estiver entre agora e agora + dias delta.

## Categoria

Data

## Sintaxe da função

`inNextDays(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inNextDays(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna verdadeiro.
