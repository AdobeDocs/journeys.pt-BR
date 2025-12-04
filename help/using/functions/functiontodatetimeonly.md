---
product: adobe campaign
title: toDateTimeOnly
description: Saiba mais sobre a função toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 15%

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
| data e hora no formato ISO-8601 ou &quot;AAAA-MM-DD&quot; (formato de data XDM) | sequência de caracteres |
| data e hora | dateTime |

## Assinaturas e tipos retornados

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Retorna um datetime sem considerar o fuso horário.

## Exemplos

`toDateTimeOnly ("2016-08-18")`

retorna um dateTime representando 2016-08-18T00:00:00.000

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
