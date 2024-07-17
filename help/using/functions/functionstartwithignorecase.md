---
product: adobe campaign
title: startWithIgnoreCase
description: Saiba mais sobre a função startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 25%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Retornará true se o segundo parâmetro for um prefixo do primeiro sem considerar letras maiúsculas e minúsculas.

## Categoria

String

## Sintaxe da função

`startWithIgnoreCase(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-------------|--------|
| sequência de caracteres | sequência de caracteres |
| prefixo | sequência de caracteres |

## Assinatura e tipo retornado

`startWithIgnoreCase(<string>,<string>)`

Retornar um booleano.

## Exemplo

`startWithIgnoreCase("rowing is great", "RO")`

Retorna verdadeiro.
