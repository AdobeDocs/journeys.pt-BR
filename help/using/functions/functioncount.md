---
product: adobe campaign
title: contagem
description: Saiba mais sobre a contagem de funções
feature: Journeys
role: Developer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 30%

---

# contagem {#count}

Conta os elementos da lista sem levar em conta os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`count(<listAny>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Assinaturas e tipo retornado

`count(<listAny>)`

Retorna um inteiro.

## Exemplo

`count([10,2,10,null])`

Retorna 3.
