---
product: adobe campaign
title: sort
description: Saiba mais sobre a classificação de função
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 18%

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
| Lista | listDateOnly |
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

`sort(<listDateOnly>,<boolean>)`

Retorna uma lista de datas.

`sort(<listBoolean>,<boolean>)`

Retorna uma lista de booleanos.

## Exemplo

`sort(["A", "C", "B"], true)`

Devoluções `["A","B","C"]`.

`sort([1, 3, 2], false)`

Devoluções `[3, 2, 1]`.
