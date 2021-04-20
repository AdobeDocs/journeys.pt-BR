---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: Saiba mais sobre a função substr
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

Retorna a substring da expressão da string entre o índice begin e o índice end. Se o índice final não estiver definido, ele estará entre o índice inicial e o final.

## Categoria

String

## Sintaxe da função

`substr(<parameters>)`

## Parâmetros

| Parâmetro | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Assinatura e tipo retornado

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retorne uma string.

## Exemplo

`substr("Hello World",6)`

Retorna &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Retorna &quot;Hello&quot;.