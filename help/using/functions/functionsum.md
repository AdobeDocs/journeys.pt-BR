---
product: adobe campaign
title: sum
description: Saiba mais sobre a soma das funções
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# sum {#sum}

Retorna a soma dos valores de um conjunto de expressões. Valores nulos são ignorados.

## Categoria

Agregação

## Sintaxe da função

`sum(<parameters>)`

## Parâmetros

* listInteger
* listDecimal
* duração
* inteiro
* decimal

## Assinaturas e tipos retornados

`sum(<listDecimal>)`

Retorna um decimal.

`sum(<listInteger>)`

Retorna um inteiro.

`sum(<integer>,<integer>)`

Retorna um inteiro.

`sum(<decimal>,<decimal>)`

Retorna um decimal.

## Exemplos

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Retorna 21.

`sum([10.5,null,8.1])`

Retorna 18,6.
