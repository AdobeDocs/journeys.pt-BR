---
product: adobe campaign
title: inNextMonths
description: Saiba mais sobre a função em NextMonths
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 15%

---

# inNextMonths {#inNextMonths}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora + meses delta.

## Categoria

Data

## Sintaxe da função

`inNextMonths(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextMonths(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Retorna true.
