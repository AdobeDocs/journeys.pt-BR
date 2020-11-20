---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: Saiba mais sobre a função emLastHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 11%

---


# inLastHours {#inLastHours}

Retorna true se a hora de data especificada estiver entre agora e agora - horas delta.

## Categoria

Data

## Sintaxe da função

`inLastHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inLastHours(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Retorna true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Retorna true.
