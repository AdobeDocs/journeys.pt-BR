---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: Saiba mais sobre a função distinctCount
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%

---


# distinctCount{#distinctCount}

Conta o número de valores diferentes que ignoram os valores nulos.

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

## Assinatura e tipo retornado

`distinctCount(<listAny>)`

Retorna um número inteiro.

## Exemplo

`distinctCount([10,2,10,null])`

Retorna 2.
