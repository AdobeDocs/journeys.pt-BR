---
product: adobe campaign
title: getListItem
description: Saiba mais sobre a função gstListItem
feature: Journeys
role: Developer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
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
source-wordcount: '93'
ht-degree: 19%
---
# getListItem {#gestListItem}

Retorna o item da lista no índice fornecido.

## Categoria

Lista

## Sintaxe da função

`getListItem(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| índice | inteiro |

## Assinaturas e tipo retornado

`getListItem(<listInteger>,<index>)`

Retorna um inteiro.

`getListItem(<listDecimal>,<index>)`

Retorna um decimal.

`getListItem(<listString>,<index>)`

Retorna uma string.

`getListItem(<listDateTimeOnly>,<index>)`

Retorna uma data e hora sem considerar o fuso horário.

`getListItem(<listDateTime>,<index>)`

Retorna um datetime.

`getListItem(<listDateOnly>,<index>)`

Retorna uma lista de datas.

`getListItem(<listBoolean>,<index>)`

Retorna um valor booleano.

`getListItem(<listDuration>,<index>)`

Retorna uma duração.

## Exemplo

`getListItem([10, 2, 3], 1)`

Retorna &quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
Retorna &quot;C&quot;

Exemplos com um campo de evento &quot;event.appVersion&quot; com valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retorna `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Retorna &quot;20&quot;
