---
title: containWithIgnoreCase
description: Saiba mais sobre a função containsWithIgnoreCase
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
source-wordcount: '48'
ht-degree: 10%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Verifica se a segunda string de argumento está contida na primeira string de argumento, sem levar em conta o caso.

## Categoria

String

## Sintaxe da função

`containWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| sequência pesquisada | string |

## Assinatura e tipo retornado

`containWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`containWithIgnoreCase("rowing is great', "GREAT")`

Retorna true.
