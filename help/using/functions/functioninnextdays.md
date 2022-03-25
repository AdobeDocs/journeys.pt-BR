---
product: adobe campaign
title: inNextDays
description: Saiba mais sobre a função em NextDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inNextDays {#inNextDays}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora + dias delta.

## Categoria

Data

## Sintaxe da função

`inNextDays(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextDays(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna true.
