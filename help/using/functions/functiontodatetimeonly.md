---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: Saiba mais sobre a função toDateTime
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
