---
product: adobe campaign
title: inNextMonths
description: Saiba mais sobre a função inNextMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

Retorna verdadeiro se uma determinada data ou dateTime estiver entre agora e agora + meses delta.

## Categoria

Data

## Sintaxe da função

`inNextMonths(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inNextMonths(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Retorna verdadeiro.
