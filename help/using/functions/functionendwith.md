---
product: adobe campaign
title: endWith
description: Saiba mais sobre a função endWith
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

Retornará true se o segundo parâmetro for um sufixo do primeiro.

## Categoria

String

## Sintaxe da função

`endWith(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|------------------|
| sequência de caracteres | sequência de caracteres |
| sufixo | sequência de caracteres |

## Assinatura e tipo retornado

`endWith(<string>,<string>)`

Retorna um valor booleano.

## Exemplo

`endWith("Hello World", "World")`

Retorna verdadeiro.

`endWith("Hello World", "Hello")`

Retorna falso.
