---
product: adobe campaign
title: startWith
description: Saiba mais sobre a função startWith
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
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
