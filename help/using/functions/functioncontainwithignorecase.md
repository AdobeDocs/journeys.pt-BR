---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Saiba mais sobre a função containsWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
