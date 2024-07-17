---
product: adobe campaign
title: toDateTime
description: Saiba mais sobre a função toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 2aa73498f44f22a70bb2268afca7d1a62e434542
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 11%

---

# toDateTime {#toDateTime}

Converte parâmetros em um valor de data e hora, dependendo de seus tipos.

## Categoria

Conversão

## Sintaxe da função

`toDateTime(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| data e hora no formato ISO-8601 | sequência de caracteres |
| id do fuso horário | sequência de caracteres |
| data hora sem fuso horário | dateTimeOnly |
| valor inteiro de uma época em milissegundos | inteiro |

>[!NOTE]
>
>A ID do fuso horário deve ser uma constante de sequência. Não pode ser uma referência de campo nem uma expressão. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

## Assinaturas e tipos retornados

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

Retornar um **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Exemplos

`toDateTime ("2016-08-18T23:17:59.123Z")`

Retorna 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

Retorna 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Retorna 17T09:03:10.189Z de 2019

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
