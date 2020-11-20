---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: Saiba mais sobre a função em LastDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inLastDays {#inLastDays}

Retorna true se determinada data ou dateTime estiver entre agora e agora - dias delta.

## Categoria

Data

## Sintaxe da função

`inLastDays(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inLastDays(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Retorna true.
