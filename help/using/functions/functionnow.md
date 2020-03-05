---
title: now
description: Saiba mais sobre a função agora
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8

---


# now {#now}

Retorna a data atual no formato de data e hora. Para obter mais informações sobre tipos de dados, consulte [](../expression/data-types.md).

## Categoria

Data

## Sintaxe da função

`now(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string |  |

## Assinaturas e tipo retornado

`now()`

`now("<timeZone id>")`

Retorna dateTime.

## Exemplos

`now()`

Retorna 2019-06-03T06:30Z.

`toString(now())`

Retorna &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Retorna 2019-06-03T08:30+02:00.