---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Saiba mais sobre a função endWith
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 12%

---


# endWith {#endWith}

Retorna true se o segundo parâmetro for um sufixo do primeiro.

## Categoria

String

## Sintaxe da função

`endWith(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| string | string |
| sufixo | string |

## Assinatura e tipo retornado

`endWith(<string>,<string>)`

Retorna um booleano.

## Exemplo

`endWith("Hello World", "World")`

Retorna true.

`endWith("Hello World", "Hello")`

Retorna false.
