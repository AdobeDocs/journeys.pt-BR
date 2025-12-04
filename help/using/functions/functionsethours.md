---
product: adobe campaign
title: setHours
description: Saiba mais sobre a função setHours
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 9%

---

# setHours {#setHours}

Define apenas as horas de uma data e hora ou data e hora. Por exemplo, se você quiser aguardar até uma determinada hora amanhã, poderá forçar a hora.

## Categoria

Data

## Sintaxe da função

`setHours(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data e hora | dateTime |
| data hora sem considerar o fuso horário | dateTimeOnly |
| horas | inteiro |

## Assinaturas e tipo retornado

`setHours(<dateTime>,<hours>)`

Retorna um datetime.

`setHours(<dateTimeOnly>,<hours>)`

Retorna uma data e hora sem considerar o fuso horário.

## Exemplos

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Retorna amanhã às 20h00, sendo XY os minutos no momento da avaliação de hora atual. :XY Se a avaliação ocorrer às 2:45 AM, a hora retornada será 20:45 PM.
