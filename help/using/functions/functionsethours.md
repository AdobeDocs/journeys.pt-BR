---
product: adobe campaign
title: setHours
description: Saiba mais sobre a função setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

---

# setHours {#setHours}

Define somente as horas de uma data ou hora de data. Por exemplo, se você quiser esperar até uma determinada hora amanhã, você pode forçar a hora.

## Categoria

Data

## Sintaxe da função

`setHours(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data e hora | dateTime |
| data e hora sem considerar fuso horário | dateTimeOnly |
| horas | inteiro |

## Assinaturas e tipo retornado

`setHours(<dateTime>,<hours>)`

Retorna um datetime.

`setHours(<dateTimeOnly>,<hours>)`

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Retorna amanhã às 8hXY PM, sendo XY os minutos no momento da avaliação atual. Se a avaliação ocorrer às 2:45 da manhã, o horário retornado será 20:45.
