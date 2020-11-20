---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: Saiba mais sobre a função startWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---


# startWithIgnoreCase {#startWithIgnoreCase}

Retorna true se o segundo parâmetro for um prefixo do primeiro sem considerar letras maiúsculas e minúsculas.

## Categoria

String

## Sintaxe da função

`startWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-------------|--------|
| string | string |
| prefixo | string |

## Assinatura e tipo retornado

`startWithIgnoreCase(<string>,<string>)`

Retorne um booleano.

## Exemplo

`startWith("rowing is great', "RO")`

Retorna true.
