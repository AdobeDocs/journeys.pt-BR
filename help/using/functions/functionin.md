---
product: adobe campaign
solution: Journey Orchestration
title: in
description: Saiba mais sobre a função em
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 13%

---


# in {#in}

Verifica se o primeiro valor do argumento está na lista. A verificação é executada por meio de um Igual em cada valor de argumento. Retorna true se o valor do argumento for encontrado, caso contrário, retornará false.

O tipo de `<expression>` deve corresponder aos itens da lista. Os tipos de itens da lista, como lembrete, devem corresponder entre si.

## Categoria

Lista

## Sintaxe da função

`in(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| String | String |
| Booleano | Booleano |
| Número inteiro | Número inteiro |
| Decimal | Decimal |
| Duração | Duração |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Assinatura e tipo retornado

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Retorne um booleano.

## Exemplo

`in(4,[4,5,3,4])`

Retorna true.

`in(8,[4,5,3,4])`

Retorna false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
