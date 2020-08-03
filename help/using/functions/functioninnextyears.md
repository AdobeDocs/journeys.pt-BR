---
title: inNextYears
description: Saiba mais sobre a função em Próximos Anos
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
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# inNextYears {#inNextYears}

Retorna true se determinada data ou dateTime estiver entre agora e agora + anos delta.

## Categoria

Data

## Sintaxe da função

`inNextYears(<dateTime>,<delta>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data hora | dateTime |
| delta | integer |

## Assinaturas e tipo retornado

`inNextYears(<dateTime>,<integer>)`

Retorna um booleano.

## Exemplos

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Retorna true.
