---
product: adobe campaign
title: containIgnoreCase
description: Saiba mais sobre a função containIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 22%

---

# containIgnoreCase {#containIgnoreCase}

Verifica se a segunda cadeia de caracteres do argumento está contida na primeira cadeia de caracteres do argumento, sem levar em conta maiúsculas e minúsculas.

## Categoria

String

## Sintaxe da função

`containIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| sequência de caracteres | sequência de caracteres |
| sequência de caracteres pesquisada | sequência de caracteres |

## Assinatura e tipo retornado

`containIgnoreCase(<string>,<string>)`

Retorna um valor booleano.

## Exemplo

`containIgnoreCase("rowing is great", "GREAT")`

Retorna verdadeiro.
