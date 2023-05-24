---
product: adobe campaign
title: split
description: Saiba mais sobre a divisão de função
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

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
| string de entrada | string |
| sequência de caracteres separadora | string |

## Assinaturas e tipo retornado

`split(<input string>, <separator string>)`

Retorna uma listString.

## Exemplo

`split(["A_B_C"], "_")`

Devoluções `["A","B","C"]`

Exemplo com um campo de evento &quot;event.appVersion&quot; com valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devoluções `["20", "45", "2", "3434"]`
