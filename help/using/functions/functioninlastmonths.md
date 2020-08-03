---
title: inLastMonths
description: Saiba mais sobre a função em LastMonths
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inLastMonths {#inLastMonths}

Retorna true se determinada data ou dateTime estiver entre agora e agora - meses delta.

## Categoria

Data

## Sintaxe da função

`inLastMonths(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inLastMonths(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Retorna true.
