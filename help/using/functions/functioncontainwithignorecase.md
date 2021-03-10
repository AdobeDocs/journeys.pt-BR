---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Saiba mais sobre a função containWithIgnoreCase
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Verifica se a segunda string de argumento está contida na primeira string de argumento, sem considerar o caso.

## Categoria

String

## Sintaxe da função

`containWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| string pesquisada | string |

## Assinatura e tipo retornado

`containWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`containWithIgnoreCase("rowing is great', "GREAT")`

Retorna true.
