---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Saiba mais sobre a função setHours
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 7%

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
| horas | integer |

## Assinaturas e tipo retornado

`setHours(<dateTime>,<hours>)`

Retorna um datetime.

`setHours(<dateTimeOnly>,<hours>)`

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Retorna 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Retorna amanhã às 20:00.
