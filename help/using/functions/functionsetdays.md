---
title: setDays
description: Saiba mais sobre a função setDays
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
source-wordcount: '74'
ht-degree: 8%

---


# setDays {#setDays}

Define somente o dia de uma data, hora ou data. Por exemplo, se você quiser esperar até um determinado dia do mês, você pode forçar o dia.

## Categoria

Data

## Sintaxe da função

`setDays(<parameter>)`

## Parâmetros

| Parâmetro | Tipo |
|--- |--- |
| data hora | dateTime |
| data e hora sem considerar o fuso horário | dateTimeOnly |
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
