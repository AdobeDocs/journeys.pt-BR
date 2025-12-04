---
product: adobe campaign
title: sort
description: Saiba mais sobre a classificação de função
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 8%

---

# sort {#sort}

Classifica uma lista de valores ou objetos na ordem natural.

## Categoria

Lista

## Sintaxe da função

`sort(<parameters>)`

## Parâmetros

| Parâmetro | Tipo | Descrição |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly ou listObject | Lista para classificar. Para listObject, ele deve ser uma referência de campo. |
| keyAttributeName | sequência de caracteres | Este parâmetro é somente para listObject. O nome do atributo nos objetos da lista fornecida é usado como chave para classificação. |
| sortingOrder | booleano | Crescente (verdadeiro) ou decrescente (falso) |

## Assinatura e tipo retornado

`sort(<listInteger>,<boolean>)`

Retorna uma lista de inteiros.

`sort(<listDecimal>,<boolean>)`

Retorna uma lista de decimais.

`sort(<listString>,<boolean>)`

Retorna uma lista de strings.

`sort(<listDateTimeOnly>,<boolean>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`sort(<listDateTime>,<boolean>)`

Retorna uma lista de datetimes.

`sort(<listDateOnly>,<boolean>)`

Retorna uma lista de datas.

`sort(<listBoolean>,<boolean>)`

Retorna uma lista de booleanos.

`sort(<listObject>,<string>,<boolean>)`

Retorna uma lista de objetos.

## Exemplo

`sort(["A", "C", "B"], true)`

Retorna `["A","B","C"]`.

`sort([1, 3, 2], false)`

Retorna `[3, 2, 1]`.

