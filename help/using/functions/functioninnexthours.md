---
product: adobe campaign
title: inNextHours
description: Saiba mais sobre a função em NextHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextHours {#inNextHours}

Retorna verdadeiro se uma determinada data ou dateTime estiver entre agora e agora + horas delta.

## Categoria

Data

## Sintaxe da função

`inNextHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | inteiro |

## Assinaturas e tipo retornado

`inNextHours(<dateTime>,<integer>)`

Retorna um valor booleano.

## Exemplos

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna verdadeiro.
