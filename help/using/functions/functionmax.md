---
title: max
description: Saiba mais sobre a função max
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
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

Retorna o valor máximo entre um conjunto de expressões, dado como uma lista ou duas expressões. Valores nulos são ignorados.

## Categoria

Agregação

## Sintaxe da função

`max(<parameter>)`

## Parâmetros

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duração
* integer
* decimal
* dateTime
* dateTimeOnly

## Assinaturas e tipos retornados

`max(<listDuration>)`

Retorna uma duração.

`max(<listInteger>)`

Retorna uma duração.

`max(<listDateTimeOnly>)`

Retorna um datetime sem considerar o fuso horário.

`max(<listDateTime>)`

Retorna um datetime.

`max(<listDecimal>)`

Retorna um decimal.

`max(<decimal>,<decimal>)`

Retorna um decimal.

`max(<duration>,<duration>)`

Retorna uma duração.

`max(<dateTime>,<dateTime>)`

Retorna um datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Retorna um datetime sem considerar o fuso horário.

`max(<integer>,<integer>)`

Retorna um número inteiro.

## Exemplos

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Retorna 10.

`max([10,null,8])`

Retorna 10.
