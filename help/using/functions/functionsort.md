---
title: sort
description: Saiba mais sobre a classificação de função
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%

---


# sort {#sort}

Classifica uma lista de valores na ordem natural. O primeiro argumento é a lista de valores, o segundo é um valor booliano que indica se a classificação é ascendente (true) ou descendente (false).

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

Retorna uma lista de strings.

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
