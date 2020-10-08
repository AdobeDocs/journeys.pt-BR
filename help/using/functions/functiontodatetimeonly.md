---
title: toDateTimeOnly
description: Saiba mais sobre a função toDateTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# toDateTimeOnly{#toDateTimeOnly}

Converte um valor de argumento em um valor somente de data e hora.

## Categoria

Conversão

## Sintaxe da função

`toDateTimeOnly(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora no formato ISO-8601 | string |
| data hora | dateTime |

## Assinaturas e tipos retornados

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Retorna 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
