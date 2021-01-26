---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Saiba mais sobre a função gstListItem
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 11%

---


# getListItem {#gestListItem}

Retorna o item da lista no índice especificado.

## Categoria

Lista

## Sintaxe da função

`getListItem(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| lista | listString |
| lista | listBoolean |
| lista | listInteger |
| lista | listDecimal |
| lista | listDuration |
| lista | listDateTime |
| lista | listDateTimeOnly |
| index | integer |

## Assinaturas e tipo retornado

`getListItem(<listInteger>,<index>)`

Retorna uma lista de números inteiros.

`getListItem(<listDecimal>,<index>)`

Retorna uma lista de decimais.

`getListItem(<listString>,<index>)`

Retorna uma lista de strings.

`getListItem(<listDateTimeOnly>,<index>)`

Retorna uma lista de datetimes sem considerar o fuso horário.

`getListItem(<listDateTime>,<index>)`

Retorna uma lista de datetimes.

`getListItem(<listBoolean>,<index>)`

Retorna uma lista de booleanos.

`getListItem(<listDuration>,<index>)`

Retorna uma lista de durações.

## Exemplo

`getListItem([10, 2, 3], 1)`

Retorna &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Retorna &quot;C&quot;

Exemplos com um campo de evento &#39;evento.appVersion&#39; com valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retorna `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Retorna &quot;20&quot;