---
product: adobe campaign
title: split
description: Saiba mais sobre a divisão de funções
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

Devoluções `["A","B","C"]`

Exemplo com um campo de evento &#39;event.appVersion&#39; com o valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devoluções `["20", "45", "2", "3434"]`
