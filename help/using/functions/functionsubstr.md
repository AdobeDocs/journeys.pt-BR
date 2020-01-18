---
title: SAA
description: Saiba mais sobre a função SAA
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# SAA {#substr}

Retorna a subsequência de caracteres da expressão de string entre o índice inicial e o índice final. Se o índice final não estiver definido, ele estará entre o índice inicial e o final.

## Categoria

Cadeia de caracteres

## Sintaxe da função

`substr(<parameters>)`

## Parâmetros

| Parâmetro | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Assinatura e tipo retornado

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retorna uma string.

## Exemplo

`substr("Hello World",6)`

Retorna &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Retorna &quot;Hello&quot;.