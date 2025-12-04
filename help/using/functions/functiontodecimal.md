---
product: adobe campaign
title: toDecimal
description: Saiba mais sobre a função toDecimal
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 14%

---

# toDecimal {#toDecimal}

Converte um valor de argumento em um valor decimal, dependendo de seu tipo.

## Categoria

Conversão

## Sintaxe da função

`toDecimal(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| sequência de caracteres | converte o valor da string em um decimal |
| dateTime | converte a data no número de milissegundos (milissegundos da época) |
| booleano | converte o valor booleano como 1 se verdadeiro, 0 se falso |
| inteiro | converte para um decimal (exemplo.: 1 torna-se 1.0) |

## Assinaturas e tipos retornados

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Retorna um decimal.

## Exemplos

`toDecimal("4.0")`

Retorna 4.0.
