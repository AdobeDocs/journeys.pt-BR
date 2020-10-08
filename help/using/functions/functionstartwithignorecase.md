---
title: startWithIgnoreCase
description: Saiba mais sobre a função startWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
