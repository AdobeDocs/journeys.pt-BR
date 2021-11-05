---
product: adobe campaign
title: inNextYears
description: Saiba mais sobre a função em NextYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inNextYears {#inNextYears}

Retorna true se uma determinada data ou dateTime estiver entre agora e agora + anos delta.

## Categoria

Data 

## Sintaxe da função

`inNextYears(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextYears(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Retorna true.
