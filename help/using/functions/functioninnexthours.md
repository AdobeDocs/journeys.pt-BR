---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: Saiba mais sobre a função em NextHours
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

---


# inNextHours {#inNextHours}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora + horas delta.

## Categoria

Data

## Sintaxe da função

`inNextHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextHours(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna true.
