---
title: setHours
description: Saiba mais sobre a função setHours
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

---


# setHours {#setHours}

Define somente as horas de uma data de hora ou data de hora. Por exemplo, se você quiser esperar até uma determinada hora amanhã, você pode forçar a hora.

## Categoria

Data

## Sintaxe da função

`setHours(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data hora | dateTime |
| data e hora sem considerar o fuso horário | dateTimeOnly |
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

Retorna amanhã às 20h.
