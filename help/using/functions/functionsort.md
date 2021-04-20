---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: Saiba mais sobre a classificação de função
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 12%

---


# sort {#sort}

Classifica uma lista de valores na ordem natural. O primeiro argumento é a lista de valores, o segundo é um valor booleano indicando se a classificação é crescente (true) ou decrescente (false).

## Categoria

Lista

## Sintaxe da função

`sort(<parameters>)`

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
| Booleano | Booleano |

## Assinatura e tipo retornado

`sort(<listInteger>,<boolean>)`

Retorna uma lista de números inteiros.

`sort(<listDecimal>,<boolean>)`

Retorna uma lista de decimais.

`sort(<listString>,<boolean>)`

Retorna uma lista de cadeias de caracteres.

`sort(<listDateTimeOnly>,<boolean>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`sort(<listDateTime>,<boolean>)`

Retorna uma lista de datetimes.

`sort(<listBoolean>,<boolean>)`

Retorna uma lista de booleanos.

## Exemplo

`sort(["A", "C", "B"], true)`

Retorna `["A","B","C"]`.

`sort([1, 3, 2], false)`

Retorna `[3, 2, 1]`.
