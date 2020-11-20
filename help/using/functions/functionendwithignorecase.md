---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: Saiba mais sobre a função endWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%

---


# endWithIgnoreCase {#endWithIgnoreCase}

Verifica se a primeira string de argumento termina com uma string específica (segunda string de argumento), não levando em consideração o caso.

## Categoria

String

## Sintaxe da função

`endWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| sufixo | string |

## Assinatura e tipo retornado

`endWithIgnoreCase(<string>,<string>)`

Retorna um booleano.

## Exemplo

`endWithIgnoreCase("rowing is great', "AT")`

Retorna true.
