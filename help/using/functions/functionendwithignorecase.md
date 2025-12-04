---
product: adobe campaign
title: endWithIgnoreCase
description: Saiba mais sobre a função endWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Verifica se a primeira sequência de argumento termina com uma sequência específica (segunda sequência de argumento), sem levar em conta maiúsculas e minúsculas.

## Categoria

String

## Sintaxe da função

`endWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| sequência de caracteres | sequência de caracteres |
| sufixo | sequência de caracteres |

## Assinatura e tipo retornado

`endWithIgnoreCase(<string>,<string>)`

Retorna um valor booleano.

## Exemplo

`endWithIgnoreCase("rowing is great", "AT")`

Retorna verdadeiro.
