---
product: adobe campaign
title: startWith
description: Saiba mais sobre a função startWith
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# startWith {#startWith}

Retornará true se o segundo parâmetro for um prefixo do primeiro.

## Categoria

String

## Sintaxe da função

`startWith(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-------------|--------|
| sequência de caracteres | sequência de caracteres |
| prefixo | sequência de caracteres |

## Assinatura e tipo retornado

`startWith(<string>,<string>)`

Retornar um booleano.

## Exemplo

`startWith("Hello World", "Hello")`

Retorna verdadeiro.

`startWith("Hello World", "World")`

Retorna falso.
