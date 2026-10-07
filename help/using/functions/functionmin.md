---
product: adobe campaign
title: min
description: Saiba mais sobre a função principal
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 7%
---
# min {#min}

Retorna o valor mínimo entre um conjunto de expressões, fornecido como uma lista ou duas expressões. Valores nulos são ignorados.

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
* listDateOnly
* duração
* inteiro
* decimal
* dateTime
* dateTimeOnly

## Assinaturas e tipos retornados

`min(<listDuration>)`

Retorna uma duração.

`min(<listInteger>)`

Retorna uma duração.

`min(<listDateTimeOnly>)`

Retorna uma data e hora sem considerar o fuso horário.

`min(<listDateTime>)`

Retorna um datetime.

`min(<listDateOnly>)`

Retorna uma data.

`min(<listDecimal>)`

Retorna um decimal.

`min(<decimal>,<decimal>)`

Retorna um decimal.

`min(<duration>,<duration>)`

Retorna uma duração.

`min(<dateTime>,<dateTime>)`

Retorna um datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Retorna uma data e hora sem considerar o fuso horário.

`min(<integer>,<integer>)`

Retorna um inteiro.

## Exemplos

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Retorna 3.

`min([10,null,8])`

Retorna 8.
