---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Saiba mais sobre o min da função
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---


# min {#min}

Retorna o valor mínimo entre um conjunto de expressões, considerando como uma lista ou duas expressões. Valores nulos são ignorados.

## Categoria

Agregação

## Sintaxe da função

`min(<parameters>)`

## Parâmetros

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duration
* integer
* decimal
* dateTime
* dateTimeOnly

## Assinaturas e tipos retornados

`min(<listDuration>)`

Retorna uma duração.

`min(<listInteger>)`

Retorna uma duração.

`min(<listDateTimeOnly>)`

Retorna um datetime sem considerar o fuso horário.

`min(<listDateTime>)`

Retorna um datetime.

`min(<listDecimal>)`

Retorna um decimal.

`min(<decimal>,<decimal>)`

Retorna um decimal.

`min(<duration>,<duration>)`

Retorna uma duração.

`min(<dateTime>,<dateTime>)`

Retorna um datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Retorna um datetime sem considerar o fuso horário.

`min(<integer>,<integer>)`

Retorna um número inteiro.

## Exemplos

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Retorna 3.

`min([10,null,8])`

Retorna 8.
