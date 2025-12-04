---
product: adobe campaign
title: inLastYears
description: Saiba mais sobre a função inLastYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastYears {#inLastYears}

Retorna verdadeiro se uma determinada data ou dateTime estiver entre agora e agora - anos delta.

## Categoria

Data

## Sintaxe da função

`inLastYears(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inLastYears(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna verdadeiro.
