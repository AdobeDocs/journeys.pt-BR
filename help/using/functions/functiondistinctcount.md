---
product: adobe campaign
title: distinctCount
description: Saiba mais sobre a função distinctCount
feature: Journeys
role: Developer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%

---

# distinctCount{#distinctCount}

Conta o número de valores diferentes ignorando os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`distinctCount(<listAny>)`

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

## Assinatura e tipo retornado

`distinctCount(<listAny>)`

Retorna um inteiro.

## Exemplo

`distinctCount([10,2,10,null])`

Retorna 2.
