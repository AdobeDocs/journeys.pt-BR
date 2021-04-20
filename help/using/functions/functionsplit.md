---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Saiba mais sobre a divisão de funções
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 8%

---


# split {#split}

Divida a primeira string de argumento por uma string separadora (segunda string de argumento, que pode ser uma expressão regular) para produzir uma lista de strings (tokens).

## Categoria

String

## Sintaxe da função

`split(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string de entrada | string |
| sequência separadora | string |

## Assinaturas e tipo retornado

`split(<input string>, <separator string>)`

Retorna listString.

## Exemplo

`split(["A_B_C"], "_")`

Retorna `["A","B","C"]`

Exemplo com um campo de evento &#39;event.appVersion&#39; com o valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retorna `["20", "45", "2", "3434"]`
