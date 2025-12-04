---
product: adobe campaign
title: split
description: Saiba mais sobre a divisão de função
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%

---

# split {#split}

Divide a primeira sequência de argumento com uma sequência de separador (segunda sequência de argumento, que pode ser uma expressão regular) para produzir uma lista de sequências de caracteres (tokens).

## Categoria

String

## Sintaxe da função

`split(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string de entrada | sequência de caracteres |
| sequência de caracteres separadora | sequência de caracteres |

## Assinaturas e tipo retornado

`split(<input string>, <separator string>)`

Retorna uma listString.

## Exemplo

`split(["A_B_C"], "_")`

Retorna `["A","B","C"]`

Exemplo com um campo de evento &quot;event.appVersion&quot; com valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retorna `["20", "45", "2", "3434"]`
