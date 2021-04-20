---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: Saiba mais sobre a função distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%

---


# distinctCountWithNull {#distinctCountWithNull}

Conta o número de valores diferentes, incluindo os valores nulos.

## Categoria

Agregação

## Sintaxe da função

`distinctCountWithNull(<listAny>)`

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

## Assinatura e tipo retornado

`distinctCountwithNull(<listAny>)`

Retorna um número inteiro.

## Exemplo

`distinctCountWithNull([10,2,10,null])`

Retorna 3.
