---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: Saiba mais sobre o avg da função
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 9%

---


# avg {#avg}

Retorna o valor médio entre um conjunto de expressões, considerando como uma lista ou duas expressões. Valores nulos são ignorados.


## Categoria

Agregação

## Sintaxe da função

`avg(<parameter>)`

## Parâmetros

Tipos compatíveis:

* listInteger
* listDecimal
* decimal
* integer

## Assinaturas e tipo retornado

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Retorna um decimal.

## Exemplos

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Retorna 7.0.

`avg(10.2, 3)`

Retorna 6.6.
