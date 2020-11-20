---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: Saiba mais sobre a função em NextHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inNextHours {#inNextHours}

Retorna true se determinada data ou dateTime estiver entre agora e agora + horas delta.

## Categoria

Data

## Sintaxe da função

`inNextHours(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextHours(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna true.
