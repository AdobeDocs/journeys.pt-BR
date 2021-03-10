---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Saiba mais sobre a função setDays
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 8%

---


# setDays {#setDays}

Define somente o dia de uma data ou hora. Por exemplo, se você quiser esperar até um determinado dia do mês, é possível forçar o dia.

## Categoria

Data

## Sintaxe da função

`setDays(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data e hora | dateTime |
| data e hora sem considerar fuso horário | dateTimeOnly |
| dias | integer |

## Assinaturas e tipo retornado

`setDays(<dateTime>,<days>)`

Retorna um datetime.

`setDays(<dateTimeOnly>,<days>)`

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Retorna 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
