---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Saiba mais sobre a função startWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 11%

---


# startWith {#startWith}

Retorna true se o segundo parâmetro for um prefixo do primeiro.

## Categoria

String

## Sintaxe da função

`startWith(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-------------|--------|
| string | string |
| prefixo | string |

## Assinatura e tipo retornado

`startWith(<string>,<string>)`

Retorne um booleano.

## Exemplo

`startWith("Hello World", "Hello")`

Retorna true.

`startWith("Hello World", "World")`

Retorna false.
