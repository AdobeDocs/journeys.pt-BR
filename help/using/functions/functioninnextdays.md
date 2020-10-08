---
title: inNextDays
description: Saiba mais sobre a função em NextDays
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
source-wordcount: '44'
ht-degree: 11%

---


# inNextDays {#inNextDays}

Retorna true se determinada data ou dateTime estiver entre agora e agora + dias delta.

## Categoria

Data

## Sintaxe da função

`inNextDays(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextDays(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retorna true.
