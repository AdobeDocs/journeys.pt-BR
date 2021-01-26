---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Saiba mais sobre a divisão de funções
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 6%

---


# split {#split}

Divide a primeira string de argumento com uma string separadora (segunda string de argumento, que pode ser uma expressão regular) para produzir uma lista de strings (tokens).

## Categoria

String

## Sintaxe da função

`split(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| cadeia de entrada | string |
| string separadora | string |

## Assinaturas e tipo retornado

`split(<input string>, <separator string>)`

Retorna listString.

## Exemplo

`split(["A_B_C"], "_")`

Retorna `["A","B","C"]`

Exemplo com um campo de evento &#39;evento.appVersion&#39; com valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retorna `["20", "45", "2", "3434"]`
