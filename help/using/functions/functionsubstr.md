---
product: adobe campaign
title: substr
description: Saiba mais sobre a função substr
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
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
source-wordcount: '65'
ht-degree: 18%
---
# substr {#substr}

Retorna a subcadeia de caracteres da expressão de cadeia de caracteres entre o índice inicial e o índice final. Se o índice final não estiver definido, ele será entre o índice inicial e o final.

## Categoria

String

## Sintaxe da função

`substr(<parameters>)`

## Parâmetros

| Parâmetro | tipo |
|-------------|----------|
| sequência de caracteres | sequência de caracteres |
| beginIndex | inteiro |
| endIndex | inteiro |

## Assinatura e tipo retornado

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retorna uma string.

## Exemplo

`substr("Hello World",6)`

Retorna &quot;Mundo&quot;.

`substr("Hello World", 0, 5)`

Retorna &quot;Olá&quot;.
