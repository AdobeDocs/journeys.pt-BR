---
product: adobe campaign
title: setDays
description: Saiba mais sobre a função setDays
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 13%

---

# setDays {#setDays}

Define apenas o dia de uma data e hora ou data e hora. Por exemplo, se você quiser aguardar até um determinado dia do mês, poderá forçar o dia.

## Categoria

Data

## Sintaxe da função

`setDays(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data e hora | dateTime |
| data hora sem considerar o fuso horário | dateTimeOnly |
| dias | inteiro |

## Assinaturas e tipo retornado

`setDays(<dateTime>,<days>)`

Retorna um datetime.

`setDays(<dateTimeOnly>,<days>)`

Retorna uma data e hora sem considerar o fuso horário.

## Exemplos

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Retorna 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
