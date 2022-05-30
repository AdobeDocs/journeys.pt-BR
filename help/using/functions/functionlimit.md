---
product: adobe campaign
title: limite
description: Saiba mais sobre o limite de funções
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# limite {#limit}

Retorna o primeiro ou o último N elementos de uma lista.

## Categoria

Lista

## Sintaxe da função

`limit(<parameters>)`

## Parâmetros

| Parâmetro | Tipo | Descrição |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly ou listObject | Lista para classificar. Para listObject, deve ser uma referência de campo. |
| numberOfItems | integer | Número de itens a serem retornados da lista fornecida. |
| firstOrLastItems | booleano | Esse parâmetro é opcional (true por padrão). true retorna os primeiros itens. falso retorna os últimos itens. |

## Assinatura e tipo retornado

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Retorna uma lista de cadeias de caracteres.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Retorna uma lista de números inteiros.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Retorna uma lista de decimais.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Retorna uma lista de booleanos.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Retorna uma lista de datas.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Retorna uma lista de datetimes.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Retorna uma lista de durações.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Retorna uma lista de objetos.

## Exemplo

`limit(["A", "B", "C", "D", "E"], 3)`

Devoluções `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Devoluções `["C","D","E"]`.
