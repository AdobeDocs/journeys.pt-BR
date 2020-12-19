---
product: adobe campaign
solution: Journey Orchestration
title: now
description: Saiba mais sobre a função agora
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# now {#now}

Retorna a data atual no formato de data e hora. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

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