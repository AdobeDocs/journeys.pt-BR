---
product: adobe campaign
title: avg
description: Saiba mais sobre a função avg
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---

# avg {#avg}

Retorna o valor médio entre um conjunto de expressões, fornecido como uma lista ou duas expressões. Valores nulos são ignorados.


## Categoria

Agregação

## Sintaxe da função

`avg(<parameter>)`

## Parâmetros

Tipos suportados:

* listInteger
* listDecimal
* decimal
* inteiro

## Assinaturas e tipo retornado

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
