---
product: adobe campaign
title: getListItem
description: Saiba mais sobre a função gstListItem
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 18%

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
| listar | listString |
| listar | listBoolean |
| listar | listInteger |
| listar | listDecimal |
| listar | listDuration |
| listar | listDateTime |
| listar | listDateTimeOnly |
| índice | integer |

## Assinaturas e tipo retornado

`getListItem(<listInteger>,<index>)`

Retorna uma lista de números inteiros.

`getListItem(<listDecimal>,<index>)`

Retorna uma lista de decimais.

`getListItem(<listString>,<index>)`

Retorna uma lista de cadeias de caracteres.

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

Exemplos com um campo de evento &#39;event.appVersion&#39; com o valor: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Devoluções `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Retorna &quot;20&quot;
